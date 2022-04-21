# **Java** 🔠

### 참고자료

- Effective JAVA 3/E


## 목차

>- [객체 생성과 파괴](#객체-생성과-파괴)
>>- [생성자 대신 정적 팩토리 메서드를 고려하기](#생성자-대신-정적-팩토리-메서드를-고려하기)
>>- [생성자에 매개변수가 많다면 빌더를 고려하기](#생성자에-매개변수가-많다면-빌더를-고려하기)
>>- [private 생성자나 열거 타입으로 싱글턴임을 보증하기](#private-생성자나-열거-타입으로-싱글턴임을-보증하기)
>>- [인스턴스화를 막을땐 private 생성자를 사용하기](#인스턴스화를-막을땐-private-생성자를-사용하기)
>>- [자원을 직접 명시하지 말고 의존 객체 주입을 사용하기](#자원을-직접-명시하지-말고-의존-객체-주입을-사용하기)
>>- [불필요한 객체 생성 피하기](#불필요한-객체-생성-피하기)
>>- [다 쓴 객체 참조는 해제하기](#다-쓴-객체-참조는-해제하기)
>>- [finalizer와 cleaner 사용은 피하기](#finalizer와-cleaner-사용은-피하기)
>>- [try-finally 보다 try-with-resources를 사용하기](#try-finally-보다-try-with-resources를-사용하기)
>- [모든 객체의 공통 메서드](#모든-객체의-공통-메서드)
>>- [equals는 일반 규약을 지켜 재정의하기](#equals는-일반-규약을-지켜-재정의하기)
>>- [equals를 재정의할땐 hashCode도 재정의하기](#equals를-재정의할땐-hashcode도-재정의하기)
>>- [toString을 항상 재정의하기](#tostring을-항상-재정의하기)
>>- [Comparable을 구현할지 고려하기](#comparable을-구현할지-고려하기)
>- [클래스와 인터페이스](#클래스와-인터페이스)
>>- [클래스와 멤버의 접근 권한을 최소화하기](#클래스와-멤버의-접근-권한을-최소화하기)
>>- [public 클래스에서는 public 필드가 아닌 접근자 메서드를 사용하기](#public-클래스에서는-public-필드가-아닌-접근자-메서드를-사용하기)

<br>

---

## 객체 생성과 파괴

### 생성자 대신 정적 팩토리 메서드를 고려하기

- 장점

  - 이름을 가질 수 있어 반환될 객체의 특성을 쉽게 묘사할 수 있음

  - 호출마다 인스턴스를 새로 생성하지 않아 성능 향상

  - 반환 타입의 하위 타입 객체를 반환할 수 있어 유연함

  - 입력 매개변수에 따라 다양한 객체를 반환할 수 있음

  - 정적 팩토리 메서드 작성 시점에 반환할 객체의 클래스가 존재하지 않아도 됨

- 단점

  - 정적 팩토리 메서드만 제공 시 상속을 할 수 없음

  - 이름만 나타나므로 원하는 메서드를 찾기 힘듬

    - 잘 알려진 규약으로 메서드 명명하여 완화

      > from, of, valueOf, getInstance, newInstance, getType, newType 등


[목차로 이동](#목차)

<br>

### 생성자에 매개변수가 많다면 빌더를 고려하기

- 객체 생성자 패턴

  - 점층적 생성자 패턴

    ```java
    public class book {
      private final String title;  // 필수
      private final String author; // 선택
      private final int price;     // 선택
      
      public book(String title) { this(title, "", 0); }
      public book(String title, String author) { this(title, author, 0); }
      public book(String title, String author, int price){
        this.title=title;
        this.author=author;
        this.price=price;
      }
    }
    ```

    - 매개변수의 개수가 많아지면 코드를 작성하거나 읽기 어려움

  - 자바빈즈 패턴

    ```java
    public class book {
      private String title="";  // 필수
      private String author=""; // 선택
      private int price=0;      // 선택
      
      public book() { }
      public void setTitle(String val) { title=val; }
      public void setAuthor(String val) { author=val; }
      public void setPrice(int val) { price=val; }
    }
    ```

    - 객체를 만들려면 메서드를 여러 개 호출해야해야함

    - 객체가 완전히 생성되기 전까지는 일관성이 무너진 상태에 놓이게 되므로 불변으로 만들 수 없음

    - 스레드에 안전적이지 않음

<br>

  - 빌더 패턴

    ```java
    public class book {
      private final String title;
      private final String author;
      private final int price;
      
      public static class Builder {
        private final String title;  // 필수
        private String author; // 선택
        private int price;     // 선택

        public Builder(String title) { this.title=title; }
        public Builder author(String val) { author=val; return this; }
        public Builder price(int val) { price=val; return this; }
        public Book build() { return new Book(this); }
      }

      private Book(Builder builder) {
        title=builder.title;
        author=builder.author;
        price=builder.price;
      }
    }
    ```

    - 빌더의 세터가 빌더 자신을 반환하기 때문에 메서드 체이닝 방식으로 연쇄적 호출 가능

      > Book book=new Book.Builder("홍길동전").author("옛날사람").price(400).build();

    ```java
    public abstract class Book {
      public enum BookType { NOVEL, ESSAY, CARTOON, TRAVELS }
      final Set<BookType> bookTypes;

      abstract static class Builder<T extends Builder<T>> {
        EnumSet<BookType> bookTypes=EnumSet.noneOf(BookType.class);
        public T addBookType(BookType bookType) {
          bookTypes.add(Objects.requireNonNull(bookType));
          return self();
        }
        abstract Book build();
        protected abstract T self(); // 형 변환 없이 메서드 체이닝을 위한 셀프타입관용구
      }
      Book(Builder<?> builder) { bookTypes=builder.bookTypes.clone(); }
    }

    public class NationalBook extend Book {
      public enum Nation { KOREA, AMERICA, CANADA, GERMANY }
      private final Nation nation;

      public static class Builder extends Book.Builder<Builder> {
        private final Nation nation;

        public Builder(Nation nation) { this.nation=Object.requireNonNull(nation); }
        @Override
        public NationBook build() { return new NationBook(this); }
        @Override
        protected Builder self() { return this; }
      }
      private NationBook(Builder builder) {
        super(builder);
        nation=builder.nation;
      }
    }

    public class SaleBook extend Book {
      public final boolean outOfPrint;

      public static class Builder extends Book.Builder<Builder> {
        private boolean outOfPrint=false; // 기본값

        public Builder outOfPrint() {
          outOfPrint=true;
          return this;
        }

        @Override
        public SaleBook build() { return new SaleBook(this); }
        @Override
        protected Builder self() { return this; }
      }
      private SaleBook(Builder builder) {
        super(builder);
        outOfPrint=builder.outOfPrint;
      }
    }
    ```

    - 계층적으로 설계된 클래스에서 함께 쓰기 좋음

    - 빌더를 이용하면 생성자로는 할 수 없는 가변인수 매개변수를 여러개 사용 가능
      
      > NationalBook nBook=new NationalBook.Builder(KOREA).addBookType(NOVEL).addBookType(CARTOON).build();   
      SaleBook sBook=new SaleBook.Builder().addBookType(GERMANY).outOfPrint().build();
    
    - 빌더 생성 비용이 크지는 않지만 객체 생성을 위해 빌더를 먼저 만들어야하므로, 성능에 민감한 경우 문제가 될 수 있음

    - 생성자나 정적 팩토리가 처리해야 할 매개변수가 많다면 빌더 패턴을 선택하는 것이 나음


[목차로 이동](#목차)

<br>

### private 생성자나 열거 타입으로 싱글턴임을 보증하기

- 싱글턴(singleton)

  > 인스턴스를 오직 하나만 생성할 수 있는 클래스

- 주의사항

  - 클래스를 싱글턴으로 만들면 이를 사용하는 클라이언트를 테스트하기 어려워질 수 있음

    > 싱글턴 인스턴스는 mock 구현으로 대체할 수 없기 때문

- 구현 방식

  - public static 멤버가 final 필드인 방식

    ```java
    public class BookSystem {
      public static final BookSystem INSTANCE= new BookSystem();
      private BookSystem() { ... } // 생성자 private

      public void leaveTheBuilding() { ... }
    }
    ```

    - 리플렉션 API인 AccessibleObject.setAccessible을 사용해 private 생성자를 호출할 수 있는 예외가 있음

      > 생성자에서 두 번째 객체 생성 시도시 예외를 던지게하여 방어함

    - 장점

      - public static 필드가 final로 해당 클래스가 싱글턴임이 API에 명백히 드러남

      - 간결함

  - 정적 팩토리 메서드를 public static 멤버로 제공하는 방식

    ```java
    public class BookSystem {
      private static final BookSystem INSTANCE= new BookSystem();
      private BookSystem() { ... } // 생성자 private
      private static BookSystem getInstance() { return INSTANCE; }

      public void leaveTheBuilding() { ... }
    }
    ```

    - 리플렉션 API인 AccessibleObject.setAccessible을 사용해 private 생성자를 호출할 수 있는 예외가 있음

      > 생성자에서 두 번째 객체 생성 시도시 예외를 던지게하여 방어함

    - 장점

      - API를 바꾸지 않고도 싱글턴이 아니게 변경할 수 있음

      - 정적 팩토리를 제네릭 싱글턴 팩토리로 만들 수 있음

      - 정적 팩토리의 메서드 참조를 공급자로 사용할 수 있음

  - 위 두 가지 방식의 문제점

    - 두 가지 방식의 싱글턴 클래스를 직렬화하려면 Serializable 인터페이스를 구현해야 할 뿐만 아니라 모든 인스턴스 필드를 transient 로 선언하고 readResolve 메서드를 제공해야 함

    > Serializable 인터페이스만 구현할 경우 직렬화된 인스턴스를 역직렬화할 때마다 새로운 인스턴스가 생성됨

  - 원소가 하나인 열거 타입을 선언하는 방식

    ```java
    public enum BookSystem {
      INSTANCE;

      public void leaveTheBuilding() { ... }
    }
    ```

    - 리플렉션 공격에서 자유로움

    - 직렬화에 추가 노력이 필요없음

    - 대부분 상황에서 원소가 하나뿐인 열거 타입이 싱글턴을 만드는 가장 좋은 방법임

    - 단점

      - 만들고자하는 싱글턴이 Enum 외의 클래스를 상속해야 한다면 사용할 수 없음

        > 모든 Enum 은 java.lang.enum 클래스를 상속하고 있기 때문임   
        다른 인터페이스를 구현하는 것은 가능함

[목차로 이동](#목차)

<br>

### 인스턴스화를 막을땐 private 생성자를 사용하기

- private 생성자를 추가하면 컴파일러가 기본 생성자를 만들지 않으므로 클래스의 인스턴스화를 막을 수 있음

  ```java
  public class UtilClass {
    // 기본 생성자가 만들어지는 것을 막는다 (인스턴스화 방지용)
    private UtilClass() {
      throw new AssertionError();
    }
  }
  ```

  - 생성자를 private으로 선언하면 하위 클래스가 상위 클래스의 생성자에 접근할 길이 막히므로 상속을 불가능하게 하는 효과도 있음

[목차로 이동](#목차)

<br>

### 자원을 직접 명시하지 말고 의존 객체 주입을 사용하기

- 의존 객체 주입이 필요한 상황

  > 클래스가 여러 자원 인스턴스를 지원해야 하며, 클라이언트가 원하는 자원을 사용해야 할 때

- 의존 객체 주입의 두 가지 형태

  >- 인스턴스를 생성할 때 생성자에 필요한 자원을 넘겨주는 형태   
  >- 생성자에 자원 팩토리를 넘겨주는 방식
  >>- 팩토리란 호출할 때마다 특정 타입의 인스턴스를 반복해서 만들어주는 객체

- 장점

  > 클래스의 유연성, 재사용성, 테스트 용이성을 훌륭히 개선해줌

[목차로 이동](#목차)

<br>

### 불필요한 객체 생성 피하기

- String 리터럴

  ```java
  String s=new String("abcdef");
  ```

  > 위 문장은 실행될 때마다 String 인스턴스를 새로 생성함   
  > 반복문이나 자주 호출되는 메서드에 있다면 쓸데없는 String 인스턴스가 수없이 만들어짐

  ```java
  String s=new String("abcdef");
  ```

  > 위 문장은 하나의 String 인스턴스를 사용할 뿐만 아니라 같은 JVM 에서 문자열 리터럴 재사용이 보장됨

- 정규표현식

  ```java
  static boolean isRomanNumeral(String s) {
    return s.matches("^(?=.)M*C[MD]|D?C{0,3})(X[CL]|L?X{0,3})(I[XV]|V?I{0,3})$");
  }
  ```

  > String.matches 의 인자로 주어진 패턴은 유한 상태 머신을 만들기 때문에 인스턴스 생성 비용이 높은데 한번쓰고 버려져서 가비지 컬렉션 대상이 되므로 성능이 중요한 상황에서 반복 사용하기엔 적절하지 않음

  ```java
  public class RomanNumerals {
    private static final Pattern ROMAN=Pattern.compile("^(?=.)M*C[MD]|D?C{0,3})(X[CL]|L?X{0,3})(I[XV]|V?I{0,3})$");
    static boolean isRomanNumeral(String s) {
      return ROMAN.matcher(s).matches();
    }
  }
  ```

  > 패턴 인스턴스를 클래스 초기화 과정에서 직접 생성해 캐싱하여 재사용함으로써 성능을 상당히 개선할 수 있음

- 오토박싱

  ```java
  private static long sum() {
    Long sum=0L;
    for(long i=0; i<=Integer.MAX_VALUE; i++)
      sum+=i;
    return sum;
  }
  ```

  > 위 코드에서 sum을 Long으로 선언해서 for 반복문 동안 오토박싱이 이루어져 2^31 개의 Long 인스턴스가 만들어짐

[목차로 이동](#목차)

<br>

### 다 쓴 객체 참조는 해제하기
> gc만 믿고 메모리 관리에 신경 쓰지 않아도 된다고 오해하면 안되는 이유
>- 자기 메모리를 직접 관리하는 클래스
>> ```java
>> public class Stack {
>>   private Object[] elements;
>>   private int size=0;
>>   private static final int DEFAULT_INITIAL_CAPACITY=16;
>>
>>   public Object pop() {
>>     if(size==0) throw new EmptyStackException();
>>     return elements[--size];
>>   }
>> }
>> ```
>>- 이슈사항
>>>- 스택이 커졌다가 줄어들었을 때 스택에서 꺼내진 객체들이 더 이상 사용되지 않더라도 gc가 회수하지 않음
>>>- 객체 참조 하나를 살려두면 gc는 그 객체가 참조하는 모든 객체(또 그 객체들이 참조하는 모든 객체)를 회수하지 못하여 잠재적으로 성능에 악영향을 줄 수 있음
>> ```java
>>   public Object pop() {
>>     if(size==0) throw new EmptyStackException();
>>     Object result=elements[--size];
>>     elements[size]=null;
>>     return result;
>>   }
>> ```
>>- 해결법
>>>- 자기 메모리를 직접 관리하는 클래스라면 항시 메모리 누수에 주의하여 원소를 사용한 즉시 그 원소가 참조한 객체들을 null처리 (참조해제) 해야함
>- 캐시
>>- 이슈사항
>>>- 객체 참조를 캐시에 넣은 사실을 잊은 채 객체 사용 후 유지
>>- 해결법
>>>- 캐시 외부에서 key를 참조하는 동안만 엔트리가 살아 있는 캐시가 필요한 상황엔 WeakHashMap 사용하여 엔트리 사용 후 즉시 제거
>>>- 시간이 지날수록 엔트리의 가치를 떨어뜨리고 사용하지 않는 엔트리를 가끔씩 제거
>- 리스너(listener) 혹은 콜백(callback)
>>- 이슈사항
>>>- 클라이언트가 콜백을 등록하고 명확히 해지하지 않으면 콜백이 계속 쌓임
>>- 해결법
>>>- 콜백을 약한 참조로 저장하여 gc가 수거할 수 있도록 함
>>>>- ex) WeakHashMap에 키로저장
>- 정리
>>- 메모리 누수는 겉으로 잘 드러나지 않아 발견하기 매우 힘들기 때문에 심각한 경우 수년간 잠복하는 사례도 있음, 따라서 예방법을 익혀두는 것이 매우 중요함

[목차로 이동](#목차)

<br>

### finalizer와 cleaner 사용은 피하기
> 자바의 두 가지 객체 소멸자
>- 이슈사항
>>- 자바는 gc가 접근할 수 없게된 객체를 회수하는 역할을 하기 때문에 finalizer와 cleaner의 두 가지 객체 소멸자는 gc에 의존하기 때문에 수행 시점과 수행 여부가 보장되지 않음
>>>- 제때 실행되어야 하는 작업에 사용 불가
>>>- 상태를 영구적으로 수정하는 작업에 사용 불가 
>>>- 객체 소멸자가 gc의 효율을 떨어뜨림
>>>- finalizer를 사용한 클래스는 finalizer 공격에 노출되어 심각한 보안 문제가 생김
>- 해결법
>>- AutoCloseable을 구현하고 try-with-resources를 사용하여 소멸 시 close 메서드를 호출하여 해결함
>- 정리
>>- 객체 소멸자는 close 메서드를 호출하지 않는것에 대비한 안전망 역할과 네이티브 피어와 연결된 객체에서만 사용하고 사용할 때도 불확실성과 성능 저하에 주의하여 신중히 고려 후 사용해야함

[목차로 이동](#목차)

<br>

### try-finally 보다 try-with-resources를 사용하기
>- 자원이 둘 이상이면 try-finally 방식은 코드가 매우 지저분해짐
>```java
>static void copy(String src, String dst) throws IOException {
>  InputStream in=new FileInputStream(src);
>  try {
>    OutputStream out=new FileOutputStream(dst);
>    try {
>      byte[] buf=new byte[BUFFER_SIZE];
>      int n;
>      while((n=int.read(buf))>=0)
>        out.write(buf, 0, n);
>    } finally {
>      out.close();
>    }
>  } finally {
>    in.close();
>  }
>}
>```
>- try-with-resources 를 사용하면 정확하고 쉽게 자원을 회수할 수 있으며 코드가 짧아지고 분명해짐
>>- 해당 자원이 AutoCloseable 인터페이스가 구현되어 있어야 사용할 수 있음
>```java
>static void copy(String src, String dst) throws IOException {
>  try (InputStream in=new FileInputStream(src);
>       OutputStream out=new FileOutputStream(dst);) {
>    byte[] buf=new byte[BUFFER_SIZE];
>    int n;
>    while((n=int.read(buf))>=0)
>      out.write(buf, 0, n);
>  }
>}
>```

[목차로 이동](#목차)

<br>

---

## 모든 객체의 공통 메서드

### equals는 일반 규약을 지켜 재정의하기
> equals 메서드는 재정의하기 쉬워 보이지만 잘못하면 치명적인 결과를 초래함
>- 재정의하지 않는것이 최선인 경우
>>- 각 인스턴스가 본질적으로 고유한 경우 (Thread)
>>- 인스턴스의 논리적 동치성을 검사할 일이 없는 경우
>>- 상위 클래스에서 재정의한 equals가 하위 클래스에서도 사용할 수 있는 경우
>>- 클래스가 private이거나 package-private(default)이고 equals 메서드를 호출할 일이 없는 경우
>- 재정의해야 하는 경우
>>- 상위 클래스의 equals가 논리적 동치성을 비교하도록 재정의되지 않았을 경우
>>>- 값이 같은 인스턴스가 둘 이상 만들어지지 않음을 보장하는 인스턴스 통제 클래스라면 equals를 재정의하지않아도 됨 (Enum)
>- equals 메서드를 재정의할 때 지켜야할 일반 규약
>>- 반사성(reflexivity) - null이 아닌 모든 참조 값 x에 대해, x.equals(x)는 true
>>- 대칭성(symmetry) - null이 아닌 모든 참조 값 x, y에 대해, x.equals(y)가 ture면 y.equals(x)도 true 
>>- 추이성(transitivity) - null이 아닌 모든 참조 값 x, y, z에 대해, x.equals(y)가 true이고 y.equals(z)도 true면 x.equals(z)도 true
>>- 일관성(consistency) - null이 아닌 모든 참조 값 x, y에 대해, x.equals(y)를 반복해서 호출하면 항상 ture를 반환하거나 항상 false를 반환
>>- null 아님 - null이 아닌 모든 참조 값 x에 대해, x.equals(null)은 false
>- 양질의 equals 메서드 구현 단계
>>- == 연산자를 사용해 입력이 자기 자신의 참조인지 확인
>>- instanceof 연산자로 입력이 올바른 타입인지 확인
>>- 입력을 올바른 타입으로 형번환
>>- 입력 객체와 자기 자신의 대응되는 핵심필드들이 모두 일치하는지 하나씩 검사
>>>- float와 double을 제외한 기본 타입 필드는 == 연산자로 비교
>>>- 참조 타입 필드는 각각의 equals 메서드로 비교
>>>- float와 double 필드는 각각 정정 메서드인 Float.compare(float, float), Double.compare(double, double)로 비교
>- 주의사항
>>- equals를 재정의할 땐 hashCode도 반드시 재정의
>>- 입력 타입이 Object가 아니라면 재정의가 아니라 다중정의이므로 주의할것
>- 구글의 AutoValue 프레임워크를 사용하여 자동으로 생성가능

[목차로 이동](#목차)

<br>

> ### equals를 재정의할땐 hashCode도 재정의하기
>- equals를 재정의한 클래스라면 hashCode도 재정의해야 함
>>- equals(Object)가 두 객체를 같다고 판단했다면, 두 객체의 hashCode는 똑같은 값을 반환해야 함
>>>- 논리적으로 같은 객체는 같은 해시코드를 반환해야 함
>- 좋은 hashCode를 작성하는 요령
>>1. int 변수 result를 선언한 후 값 c로 초기화
>>> c는 해당 객체의 첫 번째 핵심 필드를 단계 2.a 방식으로 계산한 해시코드
>>>> 핵심 필드란 equals 비교에 사용되는 필드
>>2. 해당 객체의 나머지 핵심 필드 f 각각에 대해 다음 작업을 수행
>>>- a. 해당 필드의 해시코드 c를 계산
>>>>1. 기본 타입 필드라면 Type.hashCode(f)를 수행
>>>>> Type은 해당 기본 타입의 박싱 클래스
>>>>2. 참조 타입 필드면서 이 클래스의 equals 메서드가 이 필드의 equals를 재귀적으로 호출해 비교한다면, 이 필드의 hashCode를 재귀적으로 호출   
>>>> 계산이 복잡해질것 같다면, 이 필드의 표준형을 만들어 그 표준형의 hashCode를 호출   
>>>> 필드의 값이 null이면 0을 사용
>>>>3. 필드가 배열이라면 핵심 원소 각각을 별도 필드처럼 다룸   
>>>> 이상의 규칙을 재귀적으로 적용하여 각 핵심 원소의 해시코드를 계산한 후 단계 2.b 방식으로 갱신함   
>>>> 배열에 핵심 원소가 없다면 단순한 상수(0)를 사용   
>>>> 모든 원소가 핵심 원소라면 Arrays.hashCode를 사용함
>>>- b. 단계 2.a 에서 계산한 해시코드 c로 result를 갱신함
>>>> result = 31 * result + c;
>>3. result를 반환
>>```java
>>@Override public int hashCode() {
>>  int result=Short.hashCode(areaCode);
>>  result=31*result+Short.hashCode(prefix);  
>>  result=31*result+Short.hashCode(lineNum);
>>  return result;
>>}
>>```
>- Objects 클래스는 임의의 개수만큼 객체를 받아 해시코드를 계산해주는 정적 메서드인 hash를 제공하지만 속도가 약간 느리므로 성능에 민감하지 않은 상황에서만 사용
>>```java
>>@Override
>>public int hashCode() {
>>  return Objects.hash(lineNum, prefix, areaCode);
>>}
>>```
>- 구굴의 AutoValue 프레임워크를 사용하여 자동으로 생성가능

[목차로 이동](#목차)

<br>

>### toString을 항상 재정의하기
>- toString 을 잘 구현한 클래스는 사용하기 편하고, 그 클래스를 사용한 시스템은 디버깅하기 쉬움
>>- toString 메서드는 println, printf, 문자열 연결 연산자(+), assert 구문에 넘길 때, 혹은 디버거가 객체를 출력할 때 자동으로 호출함
>>- 인스턴스를 포함한 객체에서 유용하게 쓰임
>- toString은 그 객체가 가진 주요 정보 모두를 반환하는 것이 좋음
>- toString을 구현할 때 반환값의 포맷을 문서화할지 정해야 함
>>- 입출력에 사용하거나 CSV 파일같은 데이터 객체로 저장할 수도 있음
>- 포맷의 명시 여부와 관계없는 주의사항
>>- toString의 의도를 명확히 밝힐것
>>- toString의 반환값에 포함된 정보를 얻어올 수 있는 API를 제공할 것
>>> 제공하지 않으면 반환값을 파싱해야 하므로 성능이 나빠지고 시스템에 치명적인 결과를 초래할 수 있음
>- 구글의 AutoValue 프레임워크를 사용하여 자동으로 생성가능

[목차로 이동](#목차)

<br>

>### Comparable을 구현할지 고려하기
>- Comparable 인터페이스의 하나뿐인 메서드 compareTo
>>- 단순 동치성 비교에 더해 순서까지 비교할 수 있으며 제네릭함
>>- Comparable을 구현했다는 것은 그 클래스의 인스턴스들에는 자연적인 순서가 있음을 뜻함
>- 자바 플랫폼 라이브러리의 모든 값 클래스와 열거타입은 Comparable을 구현함
>- CompareTo 메서드에서 필드의 값을 비교할 때 방식
>>- 박싱된 기본 타입 클래스가 제공하는 정적 메서드 compare 를 이용
>>- Comparator 인터페이스가 제공하는 비교자 생성 메서드를 사용할것


[목차로 이동](#목차)

<br>

---

## 클래스와 인터페이스

>### 클래스와 멤버의 접근 권한을 최소화하기
>- 잘 설계된 컴포넌트
>>- 모든 내부 구현을 완벽히 숨겨, 구현과 API를 깔끔히 분리
>>- 오직 API를 통해서 다른 컴퓨넌트와 소통하며 서로의 내부 동작 방식에는 전혀 개의치 않음
>>- 정보 은닉, 혹은 캡슐화라 부르며 소프트웨어 설계의 근간이 되는 원리
>- 정보은닉
>>- 소프트웨어가 올바로 동작하는 한 모든 클래스와 멤버의 접근성을 가능한 한 좁혀야 함
>>- 접근 제어 메커니즘은 클래스, 인터페이스, 멤버의 접근성(접근 허용 범위)을 명시
>- public 클래스는 상수용 public static final 필드 외에는 어떠한 public 필드도 가져서는 안됨
>- public static final 필드가 참조하는 객체가 불변인지 확인해야함


[목차로 이동](#목차)

<br>

>### public 클래스에서는 public 필드가 아닌 접근자 메서드를 사용하기
>- public 클래스는 절대 가변 필드를 직접 노출하면 안됨
>>- 불변 필드라면 노출해도 덜 위험하지만 완전히 안심할 수 없음
>- package-private(default) 클래스나 private 중첩 클래스에서는 종종 필드를 노출하는 것이 나을 떄도 있음

[목차로 이동](#목차)

<br>