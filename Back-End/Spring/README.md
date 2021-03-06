# **Spring** ๐

### ์ฐธ๊ณ ์๋ฃ

- ํ ๋น์ ์คํ๋ง 3.1


## ๋ชฉ์ฐจ
  - [๊ฐ์](#๊ฐ์)
    - [**Spring**์ ์ ์](#spring์-์ ์)
    - [**POJO**](#pojo)
    - [**IoC/DI**](#iocdi)
    - [**AOP**](#aop)
    - [**PSA**](#psa)
  - [ํน์ง](#ํน์ง)
    - [IoC](#ioc)
    - [Container](#container)
    - [DI](#di)
  - [MVC(Model-View-Controller)](#mvcmodel-view-controller)
    - [Spring MVC](#spring-mvc)
    - [Spring MVC ์คํ ์์](#spring-mvc-์คํ-์์)
    - [Spring MVC ๊ตฌํ](#spring-mvc-๊ตฌํ)
  - [Controller](#controller)
    - [@Controller](#controller-1)
    - [@RequestMapping](#requestmapping)
    - [HTTP method](#http-method)
    - [Controller method์ parameter type](#controller-method์-parameter-type)
    - [@RequestBody parameter type](#requestbody-parameter-type)
    - [Servlet API ์ฌ์ฉ์๊ธฐ](#servlet-api-์ฌ์ฉ์๊ธฐ)
    - [Controller Class์์ method์ return type ์ข๋ฅ](#controller-class์์-method์-return-type-์ข๋ฅ)
  - [View](#view)
  - [Model](#model)
  - [Spring Web Application์ ๋์์์](#spring-web-application์-๋์์์)
  - [FileUpload](#fileupload)
  - [FileDownload](#filedownload)
  - [Interceptor](#interceptor)
  - [MyBatis](#mybatis)
    - [Mapper Interface](#mapper-interface)
    - [MyBatis์ Spring์ ์ฐ๋](#mybatis์-spring์-์ฐ๋)
  - [REST API](#rest-api)
  - [SpringBoot](#springboot)

<br>

---

## ๊ฐ์

### **Spring**์ ์ ์

- **์๋ฐ ์ํฐํ๋ผ์ด์ฆ ๊ฐ๋ฐ์ ํธํ๊ฒ ํด์ฃผ๋ ์คํ์์ค ๊ฒฝ๋๊ธ ์ ํ๋ฆฌ์ผ์ด์ ํ๋ ์์ํฌ**

  - ์ ํ๋ฆฌ์ผ์ด์ ํ๋ ์์ํฌ

    - ํน์  ๊ณ์ธต์ด๋ ๊ธฐ์ , ์๋ฌด ๋ถ์ผ์ ๊ตญํ๋์ง ์๊ณ  ์ ํ๋ฆฌ์ผ์ด์์ ์  ์์ญ์ ํฌ๊ดํ๋ ๋ฒ์ฉ์ ์ธ ํ๋ ์์ํฌ

    - ์ ํ๋ฆฌ์ผ์ด์์ ์  ์์ญ์ ๊ดํตํ๋ ์ผ๊ด๋ ํ๋ก๊ทธ๋๋ฐ ๋ชจ๋ธ๊ณผ ํต์ฌ ๊ธฐ์ ์ ๋ฐํ์ผ๋ก ๊ฐ ๋ถ์ผ์ ํน์ฑ์ ๋ง๋ ํ์๋ฅผ ์ฑ์์ฃผ๊ณ  ์๊ธฐ ๋๋ฌธ์ ๋น ๋ฅด๊ณ  ํจ์จ์ ์ผ๋ก ๊ฐ๋ฐํ  ์ ์์

  - ๊ฒฝ๋๊ธ

    - ๋ถํ์ํ๊ฒ ๋ฌด๊ฒ์ง ์๋ค๋ ์๋ฏธ๋ก์จ ๊ธฐ์กด EJB๊ณผ ๋น๊ตํ์ฌ ๊ฐ๋ฐํ๊ฒฝ๊ณผ ๊ธฐ์ ์์ค์ด ๋น์ทํ๋๋ผ๋ ํจ์ฌ ๋น ๋ฅด๊ณ  ๊ฐํธํ๊ฒ ์์ฑํ  ์ ์์ด ์์ฐ์ฑ๊ณผ ํ์ง ๋ฉด์์ ์ ๋ฆฌํจ

  - ์๋ฐ ์ํฐํ๋ผ์ด์ฆ ๊ฐ๋ฐ์ ํธํ๊ฒ

    - ๊ฐ๋ฐ์๊ฐ ๋ณต์กํ๊ณ  ์ค์ํ๊ธฐ ์ฌ์ด ๋ก์ฐ๋ ๋ฒจ ๊ธฐ์ ์ ๋ง์ ์ ๊ฒฝ์ ์ฐ์ง ์์ผ๋ฉด์๋ ์ ํ๋ฆฌ์ผ์ด์์ ํต์ฌ์ธ ์ฌ์ฉ์์ ์๊ตฌ์ฌํญ, ์ฆ ๋น์ฆ๋์ค ๋ก์ง์ ๋น ๋ฅด๊ณ  ํจ๊ณผ์ ์ผ๋ก ๊ตฌํํ๋ ๊ฒ

### **POJO**

- Plain Old Java Object

  - Spring์ POJO๋ IoC/DI + AOP + PSA(Portable Service Abstraction) ๋ฅผ ํตํด ๊ตฌํ๋จ

  - ๊ฐ๋จํ ์๋ฐ์ค๋ธ์ ํธ๋ผ๋ ์๋ฏธ๋ก์จ ํน์  ํ๊ฒฝ๊ณผ ๊ธฐ์ ์ ์ข์๋์ง ์๊ณ  ํ์์ ๋ฐ๋ผ ์ฌํ์ฉ๋  ์ ์๋ ๋ฐฉ์์ผ๋ก ์ค๊ณ๋ ์ค๋ธ์ ํธ

- ์ฅ์ 

  - ํน์ ํ ๊ธฐ์ ๊ณผ ํ๊ฒฝ์ ์ข์๋์ง ์๋ ์ค๋ธ์ ํธ๋ ๊น๋ํ ์ฝ๋๊ฐ ๋  ์ ์์

  - ์ ์ฐํ ๋ฐฉ์์ผ๋ก ์ํ๋ ๋ ๋ฒจ์์ ๋น ๋ฅด๊ณ  ๋ชํํ๊ฒ ํ์คํธํ  ์ ์์ด ์๋ํ๋ ํ์คํธ์ ๋งค์ฐ ์ ๋ฆฌํจ

### **IoC/DI**

- Inversion of Control / Dependency Injection

- ํ์ฅ์๋ ์ด๋ ค ์๊ณ  ๋ณ๊ฒฝ์๋ ๋ซํ ์๋ OCP(๊ฐ๋ฐฉ ํ์ ์์น)์ผ๋ก ์ค๋ชํ  ์ ์์

- ์ ์ฐํ๊ฒ ํ์ฅ ๊ฐ๋ฅํ ๊ฐ์ฒด๋ฅผ ๋ง๋ค์ด ๋๊ณ  ๊ฐ์ฒด ๊ฐ์ ์์กด๊ด๊ณ๋ ์ธ๋ถ์์ ๋ค์ด๋๋ฏนํ๊ฒ ์ค์ 

### **AOP**

- Aspect Oriented Programming

- ํ๋ก์๋ฅผ ํตํด ๊ตฌํ๋๋ฉฐ ๊ด์ฌ์ฌ์ ๋ถ๋ฆฌ๋ฅผ ํตํด ์ํํธ์จ์ด์ ๋ชจ๋์ฑ์ ํฅ์์์ผ ๊ณตํต ๋ชจ๋์ ์ฌ๋ฌ ์ฝ๋์ ์ฝ๊ฒ ์ ์ฉํ  ์ ์์

### **PSA**

- Portable Service Abstraction

- ๊ธฐ์ ์ ๋ณ๊ฒฝ๊ณผ ํ๊ฒฝ์ ๊ด๊ณ์์ด ์ผ๊ด๋ ๋ฐฉ์์ผ๋ก ์๋น์คํ  ์ ์๊ฒ ํ๋ ์ค๊ณ ์์น

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

## ํน์ง

- ๊ฒฝ๋์ปจํ์ด๋

  - ์คํ๋ง์ ์๋ฐ๊ฐ์ฒด๋ฅผ ๋ด๊ณ  ์๋ ์ปจํ์ด๋

  - ์คํ๋ง ์ปจํ์ด๋๋ ์๋ฐ ๊ฐ์ฒด์ ๋ผ์ดํ์ฌ์ดํด์ ๊ด๋ฆฌํจ

- POJO ์ง์

  - ํน์  ์ธํฐํ์ด์ค๋ฅผ ๊ตฌํํ๊ฑฐ๋ ๋๋ ํด๋์ค๋ฅผ ์์ํ์ง ์๋ ์ผ๋ฐ ์๋ฐ ๊ฐ์ฒด ์ง์

- IoC (Inversion of Control - ์ ์ด์ ์ญ์ )

  - ๊ฐ๋ฐ์์๊ฒ ์๋ ๊ฐ์ฒด ์์ฑ ๋ฐ ์์กด ๊ด๊ณ ์ ์ด๊ถ์ ์ปจํ์ด๋์๊ฒ ๋งก๊น

  - ๊ฐ์ฒด์ ์์ฑ๊ณผ ์๋ช์ฃผ๊ธฐ๋ฅผ ๊ด๋ฆฌ ํ  ์ ์์ด ์คํ๋ง ์ปจํ์ด๋๋ผ๊ณ  ๋ถ๋ฆ

- DI ํจํด ์ง์

  - ์คํ๋ง์ ์ค์  ํ์ผ์ด๋ ์ด๋ธํ์ด์์ ํตํด ๊ฐ์ฒด ๊ฐ ์์กด ๊ด๊ณ๋ฅผ ์ค์ ํ  ์ ์์ผ๋ฏ๋ก ์ง์  ์์ฑํ๊ฑฐ๋ ๊ฒ์ํ  ํ์๊ฐ ์์

- AOP ์ง์

  - ๋ฌธ์ ๋ฅผ ๋ฐ๋ผ๋ณด๋ ๊ด์ ์ ๊ธฐ์ค์ผ๋ก ํ๋ก๊ทธ๋๋ฐํ๋ ๊ธฐ๋ฒ

  - ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํ ํต์ฌ๊ด์ฌ ์ฌํญ๊ณผ ์ ์ฒด์ ์ ์ฉ๋๋ ๊ณตํต๊ด์ฌ ์ฌํญ์ ๋๋์ด ํ๋ก๊ทธ๋๋ฐ

  - ํ๋ก์ ๊ธฐ๋ฐ์ AOP๋ก์จ ํธ๋์ญ์, ๋ก๊น, ๋ณด์๊ณผ ๊ฐ์ ์ฌ๋ฌ ๋ชจ๋์์ ๊ณตํต์ผ๋ก ํ์๋ก ํ์ง๋ง ๋ชจ๋์ ํต์ฌ์ด ์๋ ๊ธฐ๋ฅ๋ค์ ๋ถ๋ฆฌํ์ฌ ๊ฐ ๋ชจ๋์ ์ ์ฉ

  - JMS, ๋ฉ์ผ, ์ค์ผ์ฅด๋ง ๋ฑ ์ํฐํ๋ผ์ด์ฆ ์ ํ๋ฆฌ์ผ์ด์ ๊ฐ๋ฐ์ ํ์ํ ๋ค์ํ API๋ฅผ ์ค์  ํ์ผ๊ณผ ์ด๋ธํ์ด์์ ํตํด ์์ฝ๊ฒ ์ฌ์ฉํ  ์ ์์

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

## IoC

- IoC ๊ฐ๋

  - ๊ฐ์ฒด ๊ฐ์ ๊ฐํ ๊ฒฐํฉ์ ๋คํ์ฑ์ผ๋ก ์ธํฐํ์ด์ค๋ฅผ ํธ์ถํ์ฌ ๊ฒฐํฉ๋๋ฅผ ๋ฎ์ถค

  - ๊ฐ์ฒด ๊ฐ์ ๊ฐํ ๊ฒฐํฉ์ ํฉํ ๋ฆฌ๋ฅผ ํธ์ถํ์ฌ ๊ฒฐํฉ๋๋ฅผ ๋ฎ์ถค

  - ๊ฐ์ฒด ๊ฐ์ ๊ฐํ ๊ฒฐํฉ์ Assembler๋ฅผ ํตํด ๊ฒฐํฉ๋๋ฅผ ๋ฎ์ถค

- IoC ๋ฐฉ๋ฒ

  - Dependency Lookup

    > ์ปจํ์ด๋๊ฐ lookup context๋ฅผ ํตํด ํ์ํ ๋ฆฌ์์ค๋ ์ค๋ธ์ ํธ๋ฅผ ์ป๋ ๋ฐฉ์

    - JNDI Lookup

  - Dependency Injection

    > ์ปจํ์ด๋๊ฐ ์ง์  ์์กด ๊ตฌ์กฐ๋ฅผ ์ค๋ธ์ ํธ์ ์ค์ ํ  ์ ์๋๋ก ์ง์ ํ๋ ๋ฐฉ์

    - Setter Injection

    - Constructor Injection

    - Method Injection

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

## Container

> ๊ฐ์ฒด์ ๋ผ์ดํ์ฌ์ดํด๊ณผ ์ ํ๋ฆฌ์ผ์ด์ ์ฌ์ฉ์ ํ์ํ ์ฃผ์ ๊ธฐ๋ฅ ์ ๊ณต

- ๊ธฐ๋ฅ

  - ๋ผ์ดํ์ฌ์ดํด ๊ด๋ฆฌ

  - ์์กด ๊ฐ์ฒด ์ ๊ณต

  - ์ค๋ ๋ ๊ด๋ฆฌ

  - ์ ํ๋ฆฌ์ผ์ด์ ์คํ์ ํ์ํ ํ๊ฒฝ

- ํ์์ฑ

  - ๋น์ฆ๋์ค ๋ก์ง ์ธ ๋ถ๊ฐ ๊ธฐ๋ฅ๋ค์ ๋ํด์๋ ๋๋ฆฝ์ ์ผ๋ก ๊ด๋ฆฌ

  - ์๋น์ค look up์ด๋ Configuration์ ๋ํ ์ผ๊ด์ฑ

  - ์๋น์ค ๊ฐ์ฒด๋ฅผ ์ฌ์ฉํ๊ธฐ ์ํด ๊ฐ๊ฐ Factory ๋๋ Singleton ํจํด์ ์ง์  ๊ตฌํํ์ง ์์๋ ๋จ

- IoC Container

  - ์ค๋ธ์ ํธ์ ์์ฑ๊ณผ ๊ด๊ณ์ค์ , ์ฌ์ฉ, ์ ๊ฑฐ ๋ฑ์ ์์์ ์ ํ๋ฆฌ์ผ์ด์ ์ฝ๋ ๋์  ๋๋ฆฝ๋ ์ปจํ์ด๋๊ฐ ๋ด๋น

  - ์คํ๋ง์์ IoC๋ฅผ ๋ด๋นํ๋ ์ปจํ์ด๋์๋ BeanFactory, ApplicationContext๊ฐ ์์

- DI Container

  - DI Container๊ฐ ๊ด๋ฆฌํ๋ ๊ฐ์ฒด๋ฅผ ๋น(Bean)์ด๋ผ ํ๊ณ , ๋น๋ค์ ์๋ช์ฃผ๊ธฐ๋ฅผ ๊ด๋ฆฌํ๋ ์๋ฏธ๋ก BeanFactory๋ผ ํจ

    - ์ผ๋ฐ์ ์ผ๋ก BeanFactory ๋ณด๋ค๋ ์ด๋ฅผ ํ์ฅํ ApplicationContext๋ฅผ ์ฌ์ฉํจ

    - getBean() ๋ฉ์๋๊ฐ ์ ์๋์ด ์์

  - BeanFactory์ ์ฌ๋ฌ ๊ฐ์ง ์ปจํ์ด๋ ๊ธฐ๋ฅ์ ์ถ๊ฐํ์ฌ ApplicationContext๋ผ ํจ

    - Spring์ด ์ ๊ณตํ๋ ApplicationContext ๊ตฌํ ํด๋์ค๋ ์ฌ๋ฌ๊ฐ์ง ์ข๋ฅ๊ฐ ์์

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

## DI

- ๋น ์์ฑ๋ฒ์

  ๋ฒ์|์ค๋ช
  :--|:--
  singleton|์ปจํ์ด๋๋น ์ธ์คํด์ค ์์ฑ (default)
  prototype|๋น ์์ฒญ์๋ง๋ค ์ธ์คํด์ค ์์ฑ
  request|HTTP Request๋ณ ์ธ์คํด์ค ์์ฑ
  session|HTTP Session๋ณ ์ธ์คํด์ค ์์ฑ

  ```java
  @Scope("prototype")
  public class UserServiceImpl implements UserService {
  }
  ```

  ```xml
  <bean id="userService" class="com.user.service.UserServiceImpl" scope="prototype"/>
  ```

- ์คํ๋ง ๋น ์ค์  ๋ฉํ์ ๋ณด

  - IoC Container

    - BeanDefinition meta data

      - XML Document

      - Annotation

      - Java Code

- ๋น ์ค์  ๋ฐฉ๋ฒ

  - XML
    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <beans xmlns="http://www.springframework.org/schema/beans"
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xsi-schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans-4.3.xsd">

      <bean id="userDao" class="com.user.dao.UserDaoImpl"/>
      
      <bean id="userService" class="com.user.service.UserServiceImpl" scope="prototype">
        <property name="userDao" ref="userDao"/>
      </bean>
    </beans>
    ```
    ```java
    ApplicationContext context=new ClassPathXmlApplicationContext("com/user/applicationContext.xml");
    CommonService userService=context.getBean("userServcie", UserService.class);

    // Resource resource=new ClassPathResouce("com/user/applicationContext.xml");
    // BeanFactory factory=new XmlBeanFactory(resource);
    // CommonService userService=(UserService)factory.getBean("userService");
    ``` 

  - Annotation
    ```java
    @Component
    public class UserServiceImpl implements UserService {
      @Autowired
      private UserDao userDao;
    }
    ```
    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <beans xmlns="http://www.springframework.org/schema/beans"
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xsi-schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans-4.3.xsd">

      <context:component-scan base-package="com.user.*"/>
    </beans>
    ``` 
    
    Stereotype|๋์
    :--|:--
    @Repository|Data Access Layer์ DAO ๋๋ Repository ํด๋์ค์ ์ฌ์ฉ
    @Service|Service Layer์ ํด๋์ค์ ์ฌ์ฉ
    @Controller|Presentation Layer์ MVC Controller์ ์ฌ์ฉ
    @Component|Layer ๊ตฌ๋ถ์ ์ ์ฉํ๊ธฐ ์ด๋ ค์ด ์ผ๋ฐ์ ์ธ ๊ฒฝ์ฐ์ ์ฌ์ฉ

    - annotation์ ๊ตฌ๋ถํ๋ ์ด์ 

      - ๊ณ์ธต๋ณ๋ก ๋น์ ํน์ฑ์ด๋ ์ข๋ฅ๋ฅผ ๊ตฌ๋ถ

      - AOP Pointcut ํํ์์ ์ฌ์ฉํ๋ฉด ํน์  annotation์ด ๋ฌ๋ฆฐ ํด๋์ค๋ง ์ค์  ๊ฐ๋ฅ

      - ํน์  ๊ณ์ธต์ ๋น์ ๋ถ๊ฐ๊ธฐ๋ฅ์ ๋ถ์ฌํ  ์ ์์

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

> ## MVC(Model-View-Controller)
>- MVC๋?
>>- Application์ ์ํํ ํ์ฅ์ ์ํด Model, View, Controller 3๊ฐ์ง ์์ญ์ผ๋ก ๋ถ๋ฆฌํจ
>>- Component์ ๋ณ๊ฒฝ์ด ๋ค๋ฅธ ์์ญ Component์ ์ํฅ์ ๋ฏธ์น์ง ์์ ์ ์ง๋ณด์์ ์ฉ์ดํจ
>>- ์ปดํฌ๋ํธ ๊ฐ์ ๊ฒฐํฉ์ฑ์ด ๋ฎ์ ํ๋ก๊ทธ๋จ ์์ ์ด ์ฉ์ดํ์ฌ ํ์ฅ์ฑ์ด ๋ฐ์ด๋จ
>- ์ฅ์ 
>>- ํ๋ฉด๊ณผ ๋น์ฆ๋์ค ๋ก์ง์ ๋ถ๋ฆฌํ์ฌ ์์ ๊ฐ๋ฅ 
>>- ์์ญ๋ณ ๊ฐ๋ฐ๋ก ์ธํ์ฌ ํ์ฅ์ฑ์ด ๋ฐ์ด๋จ
>>- ํ์คํ๋ ์ฝ๋๋ฅผ ์ฌ์ฉํ๋ฏ๋ก ๊ณต๋์์์ด ์ฉ์ดํ๊ณ  ์ ์ง๋ณด์์ฑ์ด ์ข์
>- ๋จ์ 
>>- ๊ฐ๋ฐ๊ณผ์ ์ด ๋ค์ ๋ณต์กํ์ฌ ์ด๊ธฐ ๊ฐ๋ฐ์๋๊ฐ ๋ฆ์
>>- ์ด๋ณด์๊ฐ ์ดํดํ๊ณ  ๊ฐ๋ฐํ๊ธฐ์ ๋ค์ ์ด๋ ค์
>- Model ์ญํ 
>>- Application ์บก์ํ
>>- ์ํ ์ฟผ๋ฆฌ์ ๋ํ ์๋ต
>>- ์ดํ๋ฆฌ์ผ์ด์์ ๊ธฐ๋ฅ ํํ
>>- ๋ณ๊ฒฝ์ view์ ํต์ง
>- View ์ญํ 
>>- Model์ ์๊ฐ์ ์ผ๋ก ํํ
>>- Model์๊ฒ ์๋ฐ์ดํธ ์์ฒญ
>>- ์ฌ์ฉ์์ ์๋ ฅ์ Controller์ ์ ๋ฌ
>>- Controller๊ฐ View๋ฅผ ์ ํํ๋๋ก ํ์ฉ
>- Controller
>>- Application์ ํ์ ์ ์
>>- ์ฌ์ฉ์ ์ก์์ Model๋ก ์๋ฐ์ดํธํ๊ณ  mapping
>>- ์๋ต์ ๋ํ View ์ ํ   
>- Model2 ์์ฒญ ํ๋ฆ ์๊ฐํ
> ![Model2 ์์ฒญ ํ๋ฆ ์ด๋ฏธ์ง](./imgs/Model2_Architecture.PNG)

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

> ### Spring MVC
>- ํน์ง
>>- Spring์ DI, AOP๊ธฐ๋ฅ ๋ฟ๋ง ์๋๋ผ, Servlet ๊ธฐ๋ฐ์ WEB ๊ฐ๋ฐ์ ์ํ MVC Framework๋ฅผ ์ ๊ณตํจ
>>- Model2 Architecture์ Front Controller Pattern์ Framework ์ฐจ์์์ ์ ๊ณตํจ
>>- Spring MVC Framework๋ Spring์ ๊ธฐ๋ฐ์ผ๋ก ํ๊ณ  ์์ด Spring์ด ์ ๊ณตํ๋ Transaction ์ฒ๋ฆฌ๋ DI, AOP๋ฑ์ ์์ฝ๊ฒ ์ฌ์ฉํ  ์ ์์
>- ๊ตฌ์ฑ์์
>>- DispatcherServlet (Front Controller)
>>>- ๋ชจ๋  ํด๋ผ์ด์ธํธ์ ์์ฒญ์ ์ฒ๋ฆฌํจ
>>>- Controller์๊ฒ ํด๋ผ์ด์ธํธ์ ์์ฒญ์ ์ ๋ฌํ๊ณ  Controller๊ฐ ๋ฆฌํดํ ๊ฒฐ๊ณผ๊ฐ์ View์๊ฒ ์ ๋ฌํ์ฌ ์๋ง์ ์๋ต์ ์์ฑํจ
>>- HandlerMapping
>>>- ํด๋ผ์ด์ธํธ์ ์์ฒญ URL์ ์ด๋ค Controller๊ฐ ์ฒ๋ฆฌํ ์ง ๊ฒฐ์ ํจ
>>>- URL๊ณผ ์์ฒญ ์ ๋ณด๋ฅผ ๊ธฐ์ค์ผ๋ก ์ด๋ค ํธ๋ค๋ฌ ๊ฐ์ฒด๋ฅผ ์ฌ์ฉํ ์ง ๊ฒฐ์ ํ๋ ๊ฐ์ฒด์ด๋ฉฐ, DispatcherServlet์ ํ๋ ์ด์์ ํธ๋ค๋ฌ ๋งคํ์ ๊ฐ์ง ์ ์์
>>- Controller
>>>- ํด๋ผ์ด์ธํธ์ ์์ฒญ์ ์ฒ๋ฆฌํ ๋ค, Model์ ํธ์ถํ๊ณ  ๊ทธ ๊ฒฐ๊ณผ๋ฅผ DispatcherServlet์ ์๋ ค์ค
>>- ModelAndView
>>>- Controller๊ฐ ์ฒ๋ฆฌํ ๋ฐ์ดํฐ ๋ฐ ํ๋ฉด์ ๋ํ ์ ๋ณด๋ฅผ ๋ณด์ ํ ๊ฐ์ฒด
>>- ViewResolver
>>>- Controller๊ฐ ๋ฆฌํดํ View ์ด๋ฆ์ ๊ธฐ๋ฐ์ผ๋ก Controller์ ์ฒ๋ฆฌ ๊ฒฐ๊ณผ๋ฅผ ๋ณด์ฌ์ค View๋ฅผ ๊ฒฐ์ 
>>- View
>>>- Controller์ ์ฒ๋ฆฌ๊ฒฐ๊ณผ๋ฅผ ๋ณด์ฌ์ค ์๋ตํ๋ฉด์ ์์ฑ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

> ### Spring MVC ์คํ ์์
>> ![Spring MVC ์์ฒญ ํ๋ฆ](./imgs/SpringMVC_Request_Flow.PNG)
>>1. DispatcherServlet ์ด ์์ฒญ์ ์์ 
>>>- ๋จ์ผ Front Controller Servlet 
>>>- ์์ฒญ์ ์์ ํ์ฌ ์ฒ๋ฆฌ๋ฅผ ๋ค๋ฅธ ์ปดํฌ๋ํธ์ ์์
>>>- ์ด๋ Controller์ ์์ฒญ์ ์ ์กํ ์ง ๊ฒฐ์ 
>>2. DispatherServlet์ด HandlerMapping์ ์ด๋ Controller๋ฅผ ์ฌ์ฉํ  ๊ฒ์ธ์ง ๋ฌธ์
>>>- URL๊ณผ Mapping
>>3. DispatcherServlet ์ ์์ฒญ์ Controller์๊ฒ ์ ์กํ๊ณ  Controller๋ ์์ฒญ์ ์ฒ๋ฆฌํ ํ ๊ฒฐ๊ณผ ๋ฆฌํด
>>>- Business Logic ์ํ ํ ๊ฒฐ๊ณผ ์ ๋ณด(Model)๊ฐ ์์ฑ๋์ด JSP์ ๊ฐ์ View์์ ์ฌ์ฉ๋จ
>>4. ModelAndView Object์ ์ํ๊ฒฐ๊ณผ๊ฐ ํฌํจ๋์ด DispatcherServelt์ ๋ฆฌํด
>>5. ModelAndView ๋ ์ค์  JSP ์ ๋ณด๋ฅผ ๊ฐ๊ณ  ์์ง ์์ผ๋ฉฐ, ViewResolver๊ฐ ๋ผ๋ฆฌ์  ์ด๋ฆ์ ์ค์  JSP์ด๋ฆ์ผ๋ก ๋ณํํจ
>>6. View๋ ๊ฒฐ๊ณผ์ ๋ณด๋ฅผ ์ฌ์ฉํ์ฌ ํ๋ฉด์ ํํํจ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

> ### Spring MVC ๊ตฌํ
>- Spring MVC๋ฅผ ์ด์ฉํ Application ๊ตฌํ ์์
>>1. web.xml์ DispatcherServlet ๋ฑ๋ก ๋ฐ Spring ์ค์ ํ์ผ ๋ฑ๋ก
>>2. ์ค์  ํ์ผ์ HandlerMapping ์ค์ 
>>3. Controller ๊ตฌํ ๋ฐ servlet-context.xml์ ๋ฑ๋ก
>>4. Controller์ JSP์ ์ฐ๊ฒฐ์ ์ํด View Resolver ์ค์ 
>>5. JSP ์ฝ๋ ์์ฑ
>- Controller ์์ฑ
>>- Controller๊ฐ ๋ง์ ์ผ์ ํ์ง ์๊ณ  Service์ ์ฒ๋ฆฌ๋ฅผ ์์ํ๋๋ก ์์ฑํ๋ค
>- web.xml -  DispatcherServlet ์ค์ 
>> ```xml
>> <servlet>
>>   <servlet-name>appServlet</servlet-name>
>>   <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
>>   <init-param>
>>     <param-name>contextConfigLocation</param-name>
>>     <param-value>/WEB-INF/spring/appServlet/servlet-context.xml</param-value>
>>   </init-param>
>>   <load-on-startup>1</load-on-startup>
>> </servlet-name>
>> 
>> <servlet-mapping>
>>   <servlet-name>appServlet</servlet-name>
>>   <url-pattern>/</url-pattern>
>> </servlet-mapping>
>> ```
>>- \<init-param>์ ์ค์ ํ์ง ์์ผ๋ฉด "\<servlet-name>-servlet.xml" ์์ applicationContext์ ์ ๋ณด๋ฅผ ๋ก๋ํจ
>>- ์คํ๋ง ์ปจํ์ด๋๋ ์ค์ ํ์ผ์ ๋ด์ฉ์ ์ฝ๊ณ  ApplicationContext๊ฐ์ฒด๋ฅผ ์์ฑํจ
>>- \<url-pattern>์ DispatcherServlet์ด ์ฒ๋ฆฌํ๋ URL Mappling pattern์ ์ ์ํจ
>> ```xml
>> <servlet>
>>   <servlet-name>appServlet</servlet-name>
>>   <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
>>   <init-param>
>>     <param-name>contextConfigLocation</param-name>
>>     <param-value>/WEB-INF/spring/appServlet/servlet-context.xml</param-value>
>>   </init-param>
>>   <load-on-startup>1</load-on-startup>
>> </servlet-name>
>> <servlet>
>>   <servlet-name>appServlet2</servlet-name>
>>   <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
>>   <init-param>
>>     <param-name>contextConfigLocation</param-name>
>>     <param-value>/WEB-INF/spring/appServlet/servlet-context2.xml</param-value>
>>   </init-param>
>>   <load-on-startup>1</load-on-startup>
>> </servlet-name>
>> 
>> <servlet-mapping>
>>   <servlet-name>appServlet</servlet-name>
>>   <url-pattern>*.do</url-pattern>
>> </servlet-mapping>
>> <servlet-mapping>
>>   <servlet-name>appServlet</servlet-name>
>>   <url-pattern>*.action</url-pattern>
>> </servlet-mapping>
>> ```
>>- ์๋ธ๋ฆฟ์ด๋ฏ๋ก 1๊ฐ ์ด์์ DispatcherServlet ์ค์  ๊ฐ๋ฅ
>>>- ๊ฐ DispatcherServlet๋ง๋ค ๊ฐ๊ฐ์ ApplicationContext ์์ฑ
>>- \<load-on-startup>1\</load-on-startup> ์ค์  ์ WAS startup ๋ ๋ ์ด๊ธฐํ ์์์ด ์งํ๋จ
>- web.xml - ์ต์์ Root ContextLoader ์ค์ 
>>- Context ์ค์  ํ์ผ๋ค์ ๋ก๋ํ๊ธฐ ์ํด web.xml ํ์ผ์ ๋ฆฌ์ค๋ ์ค์ 
>> ```xml
>> <listener>
>>   <listener-class>org.springframework.context.ContextLoaderListener</listener-class>
>> </listener>
>> ```
>>- ๋ฆฌ์ค๋ ์ค์ ์ /WEB-INF/spring/root-context.xml ํ์ผ์ ์ฝ์ด ๊ณตํต์ ์ผ๋ก ์ฌ์ฉ๋๋ ์ต์์ Context๋ฅผ ์์ฑ
>>- ๊ทธ ์ธ์ ๋ค๋ฅธ ์ปจํ์คํธ ํ์ผ๋ค์ ์ต์์ ์ดํ๋ฆฌ์ผ์ด์ ์ปจํ์คํธ์ ๋ก๋ํ๋ ๋ฐฉ๋ฒ
>>> ```xml
>>> <context-param>
>>>   <param-name>contextConfigLocation</param-name>
>>>   <param-value>
>>>     /WEB-INF/spring/root-context.xml
>>>     classpath:com/test/web/application.xml <!-- ํด๋น ํด๋์ค ํจ์ค์ ์์นํ ์ค์ ํ์ผ๋ก๋ถํฐ ๋ค๋ฅธ ์ปจํ์คํธ ํ์ผ ๋ก๋ -->
>>>   </param-value>
>>> </context-param>
>>> ```
>>> ```xml
>>> <!-- com/test/web/application.xml -->
>>> <context-param>
>>>   <param-name>contextConfigLocation</param-name>
>>>   <param-value>
>>>     /WEB-INF/spring/root-*.xml
>>>   </param-value>
>>> </context-param>
>>> ```
>- Application Context ๋ถ๋ฆฌ
>>- ์ดํ๋ฆฌ์ผ์ด์ ๋ ์ด์ด์ ๋ฐ๋ผ ์ดํ๋ฆฌ์ผ์ด์ ์ปจํ์คํธ๋ฅผ ๋ถ๋ฆฌ
>>> Layer|์ค์ ํ์ผ
>>> :--|:--
>>> Security|board-security.xml
>>> Web|board-servlet.xml
>>> Service|board-service.xml
>>> Persistence|board-dao.xml
>- Controller Class ์์ฑ
>> ```java
>> @Slf4j
>> @Controller
>> public class HomeController{
>>   //@GetMapping({"/", "/index"})
>>   @RequestMapping(value={"/", "/index"}, method=RequestMethod.GET)
>>   public String home(Model m) {
>>     log.info("๋ฐฉ๋ฌธ์์ฒญ");
>>     m.addAttribute("msg","๋ฐฉ๋ฌธํ์");
>>     return "index";
>>   }
>> }
>> ```
>- Context ์ค์ ํ์ผ์ Controller ๋ฑ๋ก (servlet-context.xml)
>> ```xml
>> <beans:bean class="com.text.web.HomeController" />
>> ```
>- Controller์ response page ์ฐ๊ฒฐ์ ์ํ ViewResolver ์ค์  (servlet-context.xml)
>> ```xml
>> <beans:bean class="com.text.web.HomeController" />
>> 
>> <beans:bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
>>   <beans:property name="prefix" value="/WEB-INF/views/" />
>>   <beans:property name="suffix" value=".jsp" />
>> </beans:bean>
>> ```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

>## Controller
>- @Controller์ @RequestMapping ์ด๋ธํ์ด์
>>- ๋ฉ์๋ ๋จ์์ mapping ๊ฐ๋ฅ
>>- DefaultAnnotationHandlerMapping๊ณผ AnnotationHandlerAdapter๋ฅผ ์ฌ์ฉ
>>>- Spring 3.0๋ถํฐ ๊ธฐ๋ณธ ์ค์ ์ด๋ฏ๋ก ๋ณ๋์ ์ค์ ์์ด ์ฌ์ฉ๊ฐ๋ฅ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### @Controller
>- Controller class๋ Client์ ์์ฒญ์ ์ฒ๋ฆฌํจ
>- Class ํ์์ ์ ์ฉ๋๋ฉฐ Spring 3.0๋ถํฐ @Controller ์ฌ์ฉ์ด ๊ถ์ฅ๋จ
>- ์ธ๋ถ ์ ์ฉ
>>- Controller Class๋ฅผ <bean>์ ๋ฑ๋ก
>>> ```xml
>>> <beans:bean id="userController" class="com.movie.user.controller.UserController">
>>>  <beans:property name="userService" ref="userService"/>
>>> </beans:bean>
>>> ```
>>- Controller Class ์๋์ค์บ
>>> ```xml
>>> <context:component-scan base-package="com.movie.user.controller" />
>>> ```
>>>- context:component-scan ์ base-package์ ์ค์ ๋ ํจํค์ง๋ด์ class์ค @Controller๊ฐ ์ ์ฉ๋ ํด๋์ค๋ ์๋์ค์บ ๋์์ด ๋จ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### @RequestMapping
>>- ์์ฒญ URL mapping ์ ๋ณด๋ฅผ ์ค์ ํ๋ฉฐ ํด๋์คํ์๊ณผ ๋ฉ์๋์ ์ค์ ํ  ์ ์์
>> ```java
>> @Controller
>> @RequestMapping("/user")
>> public class UserController {
>>  private UserService userService;
>>  
>>  //@RequestMapping("/user/regist.do")
>>  @RequestMapping("/regist.do")
>>  public String regist() {
>>    return "user/regist";
>>  }
>> }
>> ```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### HTTP method
>>- ๊ฐ์ URL ์์ฒญ์ ๋ํ์ฌ HTTP method(GET, POST..)์ ๋ฐ๋ผ ๋ค๋ฅธ ๋ฉ์๋ mapping ๊ฐ๋ฅ
>> ```java
>> @Controller
>> @RequestMapping("/user")
>> public class UserController {
>>  private UserService userService;
>>  
>>  @RequestMapping("/regist.do", method=RequestMethod.GET)
>>  public String regist() {
>>    return "user/regist";
>>  }
>>
>>  @RequestMapping("/regist.do", method=RequestMethod.POST)
>>  public String regist2() {
>>    return "user/regist";
>>  }
>> }
>> ```
>>- Controller class์ ๋งคํ์ด ๋์ด์๋๋ฐ ๋ฉ์๋์ ๋งคํ์ค์ ์ด ์์ผ๋ฉด HTTP ERROR 404
>> ```java
>> @Controller
>> @RequestMapping("/user")
>> public class UserController {
>>  private UserService userService;
>>  
>>  @RequestMapping(method=RequestMethod.GET) // HTTP ERROR 404 (Not Found)
>>  public String regist() {
>>    return "user/regist";
>>  }
>> }
>> ```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### Controller method์ parameter type
>- Controller method์ parameter๋ก ๋ค์ํ Object๋ฅผ ๋ฐ์ ์ ์์
>> Parameter Type|์ค๋ช
>> :--|:--
>> HttpServletRequest|
>> HttpServletResponse|ํ์์ Servlet API๋ฅผ ์ฌ์ฉํ  ์ ์์
>> HttpSession|
>> Java.util.Locale|ํ์ฌ ์์ฒญ์ ๋ํ ์์น๊ด๋ จ์ ๋ณด๋ฅผ ์ฌ์ฉํ  ์ ์์
>> InputStream, Reader|์์ฒญ ์ปจํ์ธ ์ ์ง์  ์ ๊ทผํ  ๋ ์ฌ์ฉ
>> OutputStream, Writer|์๋ต ์ปจํ์ธ ๋ฅผ ์์ฑํ  ๋ ์ฌ์ฉ
>> @PathVariable annotation ์ ์ฉ ํ๋ผ๋ฏธํฐ|URI ํํ๋ฆฟ ๋ณ์์ ์ ๊ทผํ  ๋ ์ฌ์ฉ
>> @RequestParam annotation ์ ์ฉ ํ๋ผ๋ฏธํฐ|HTTP ์์ฒญ ํ๋ผ๋ฏธํฐ๋ฅผ ๋งคํ
>> @RequestHeader annotation ์ ์ฉ ํ๋ผ๋ฏธํฐ|HTTP ์์ฒญ ํค๋๋ฅผ ๋งคํ
>> @CookieValue annotation ์ ์ฉ ํ๋ผ๋ฏธํฐ|HTTP ์ฟ ํค ๋งคํ
>> @RequestBody annotation ์ ์ฉ ํ๋ผ๋ฏธํฐ|HTTP ์์ฒญ์ body ๋ด์ฉ์ ์ ๊ทผํ  ๋ ์ฌ์ฉ
>> Map, Model, ModelMap|view์ ์ ๋ฌํ  model data๋ฅผ ์ค์ ํ  ๋ ์ฌ์ฉ
>> ์ปค๋งจ๋ ๊ฐ์ฒด(DTO)|HTTP ์์ฒญ parameter๋ฅผ ์ ์ฅํ ๊ฐ์ฒด
>> &nbsp;|๊ธฐ๋ณธ์ ์ผ๋ก ํด๋์ค ์ด๋ฆ์ ๋ชจ๋ธ๋ช์ผ๋ก ์ฌ์ฉ
>> &nbsp;|@ModelAttribute annotation ์ค์ ์ผ๋ก ๋ชจ๋ธ๋ช์ ์ค์ ํ  ์ ์์
>> Errors, BindingResult|HTTP ์์ฒญ ํ๋ผ๋ฏธํฐ๋ฅผ ์ปค๋งจ๋ ๊ฐ์ฒด์ ์ ์ฅํ ๊ฒฐ๊ณผ
>> &nbsp;|์ปค๋งจ๋ ๊ฐ์ฒด๋ฅผ ์ํ ํ๋ผ๋ฏธํฐ ๋ฐ๋ก ๋ค์์ ์์น
>> SessionStatue|ํผ ์ฒ๋ฆฌ๋ฅผ ์๋ฃ ํ์์ ์ฒ๋ฆฌํ๊ธฐ ์ํด ์ฌ์ฉ
>> &nbsp;|@SessionAttributes annotation์ ๋ช์ํ session ์์ฑ์ ์ ๊ฑฐํ๋๋ก ์ด๋ฒคํธ ๋ฐ์
>- @RequestParam annotation์ ์ด์ฉํ parameter mapping
>> ```java
>> @Controller
>> public class UserController {
>>  private UserService userService;
>>  
>>  // URL ํธ์ถ : http://localhost/user/regist?name=ํ๊ธธ๋&age=30
>>
>>  @RequestMapping(value="/regist" method=RequestMethod.GET)
>>  //public String regist(@RequestParam("name") String name, @RequestParam("age") int age, Model model) {
>>  public String regist(@RequestParam(value="name", required=false) String name, @RequestParam(value="age", defaultValue="25") int age, Model model) {
>>    model.addAttribute("msg", name+"("+age+")๋ ํ์ํฉ๋๋ค");
>>    return "index";
>>  }
>> }
>> ```
>- form์ ์๋ ฅํ data๋ฅผ JavaBean ๊ฐ์ฒด๋ฅผ ์ด์ฉํ์ฌ ์ ์กํ  ์ ์๊ณ  List๋ก๋ ๊ฐ๋ฅํจ
>> ```html
>> <form method="POST" action="${root}/user/regist">
>>   ์ด๋ฆ: <input type="text" name="name"><br>
>>   ๋์ด: <input type="nubmer" name="age"><br>
>>   <input type="submit" value="ํ์๊ฐ์">
>></form>
>> ```
>> ```java
>> @Controller
>> @RequestMapping("/user")
>> public class UserController {
>>   @RequestMapping(value="/regist", method=RequestMethod.POST)
>>   public String regist(UserDto userDto) {
>>     return "user/regist_result";
>>   }
>> }
>> ```
>> ```java
>> public class UserDto {
>>   private String name;
>>   private int age;
>> 
>>   //setters
>> }
>> ```
>- View์์ Command ๊ฐ์ฒด์ ์ ๊ทผ
>>- Command ๊ฐ์ฒด๋ ์๋์ผ๋ก ๋ฐํ๋๋ Model์ ์ถ๊ฐ๋๊ณ , view์์ ์ ๊ทผ์ด ๊ฐ๋ฅํจ
>- @CookieValue annotation์ ์ด์ฉํ Cookie mapping
>> ```java
>> @Controller
>> public class HomeController {
>>   //public String hello(@CookieValue("author") String authorValue) {
>>   public String hello(@CookieValue(value="author", required=false, defaultValue="user") String authorValue) {
>>     return "ok";
>>   }
>> }
>> ```
>- @RequestHeader annotation์ ์ด์ฉํ header mapping
>> ```java
>> @Controller
>> public class HomeController {
>>   public String hello(@RequestHeader("Accept-Language") String authorValue) {
>>     return "ok";
>>   }
>> }
>> ```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### @RequestBody parameter type
>- HTTP ์์ฒญ Body๊ฐ ๊ทธ๋๋ก ๊ฐ์ฒด์ ์ ๋ฌ๋จ
>- AnnotationMethodHandlerAdapter์๋ HttpMessageConverter ํ์์ ๋ฉ์์ง ๋ณํ๊ธฐ๊ฐ ๊ธฐ๋ณธ์ผ๋ก ์ฌ๋ฌ๊ฐ ๋ฑ๋ก๋์ด ์์
>- @RequestBody๊ฐ ๋ถ์ parameter๊ฐ ์์ผ๋ฉด ํด๋น ๋ฏธ๋์ด ํ์์ ํ์ธ ํ ์ฒ๋ฆฌ ๊ฐ๋ฅํ ๋ณํ๊ธฐ๊ฐ ์๋์ผ๋ก ๊ฐ์ฒด๋ก ๋ณํ์์ผ ์ค
>- ์ฃผ๋ก @ResponseBody์ ํจ๊ป ์ฌ์ฉ๋๋ฉฐ ๋น๋๊ธฐ์ฒ๋ฆฌ๋จ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### Servlet API ์ฌ์ฉ์๊ธฐ
>- HttpSession์ ์์ฑ์ ์ง์  ์ ์ดํด์ผ ํ๋ ๊ฒฝ์ฐ
>- Controller๊ฐ Cookie๋ฅผ ์์ฑํด์ผ ํ๋ ๊ฒฝ์ฐ
>- Servlet API๋ฅผ ์ ํธํ๋ ๊ฒฝ์ฐ
>- Servlet API์ ์ข๋ฅ
>>- javax.servlet.ServletRequest / javax.servlet.http.HttpServletRequest
>>- javax.servlet.ServletResponse / javax.servlet.http.HttpServletResponse
>>- javax.servlet.http.HttpSession
> ```java
> @Controller
> public class HomeController {
>   public String hello(HttpServletRequest request, HttpServletResponse response) {
>     return "ok";
>   }
> }
> ```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### Controller Class์์ method์ return type ์ข๋ฅ
> Return Type|์ค๋ช
> :--|:--
> ModelAndView|model ์ ๋ณด ๋ฐ view ์ ๋ณด๋ฅผ ๋ด๊ณ ์๋ ๊ฐ์ฒด
> Model|view์ ์ ๋ฌํ  ๊ฐ์ฒด ์ ๋ณด๋ฅผ ๋ด๊ณ ์๋ Model์ ๋ฐํํ๋ค. view์ด๋ฆ์ ์์ฒญ URL๋ก๋ถํฐ ๊ฒฐ์ ๋จ(RequestToViewNameTranslator)
> Map|view์ ์ ๋ฌํ  ๊ฐ์ฒด ์ ๋ณด๋ฅผ ๋ด๊ณ ์๋ Map์ ๋ฐํํ๋ค. view์ด๋ฆ์ ์์ฒญ URL๋ก๋ถํฐ ๊ฒฐ์ ๋จ(RequestToViewNameTranslator)
> String|view์ ์ด๋ฆ์ ๋ฐํํจ
> View|view ๊ฐ์ฒด๋ฅผ ์ง์  ๋ฆฌํด, ํด๋น View ๊ฐ์ฒด๋ฅผ ์ด์ฉํด์ view๋ฅผ ์์ฑํจ
> void|method๊ฐ ServletResponse๋ HttpServletResponseํ์์ parameter๋ฅผ ๊ฐ๋ ๊ฒฝ์ฐ method๊ฐ ์ง์  ์๋ต์ ์ฒ๋ฆฌํ๋ค๊ณ  ๊ฐ์ ํ๋ค. ๊ทธ๋ ์ง ์์ ๊ฒฝ์ฐ ์์ฒญ URL๋ก๋ถํฐ ๊ฒฐ์ ๋ View๋ฅผ ๋ณด์ฌ์ค๋ค (RequestToViewNameTranslator)
> @ResponseBody Annotation ์ ์ฉ|method์์ @ResponseBody annotation์ด ์ ์ฉ๋ ๊ฒฝ์ฐ, ๋ฆฌํด ๊ฐ์ฒด๋ฅผ HTTP ์๋ต์ผ๋ก ์ ์กํจ. HttpMessageConverter๋ฅผ ์ด์ฉํด์ ๊ฐ์ฒด๋ฅผ HTTP ์๋ต ์คํธ๋ฆผ์ผ๋ก ๋ณํํจ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

>## View
>- View ์ง์ 
>>- Controller์์๋ ์ฒ๋ฆฌ๊ฒฐ๊ณผ๋ฅผ ๋ณด์ฌ์ค View ์ด๋ฆ์ด๋ ๊ฐ์ฒด๋ฅผ ๋ฆฌํดํ๊ณ , DispatcherServlet์ View์ด๋ฆ์ด๋ View๊ฐ์ฒด๋ฅผ ์ด์ฉํ์ฌ view๋ฅผ ์์ฑ
>- ViewResolver
>>- ๋ผ๋ฆฌ์  view์ ์ค์  JSPํ์ผ mapping
>>- servlet-context.xml
>>>```xml
>>><beans:bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
>>>  <beans:property name="prefix" value="/WEB-INF/views/" />
>>>  <beans:property name="suffix" value=".jsp" />
>>></beans:bean>
>>>```
>- View ์ด๋ฆ ๋ช์์  ์ง์ 
>>- ModelAndView ์ String ๋ฆฌํด ํ์
>>>```java
>>> @Controller
>>> public class HomeController {
>>>   @RequestMapping("/hello")
>>>   public ModelAndView hello(){
>>>     ModelAndView mav=new ModelAndView("hello");
>>>     return mav;
>>>   }
>>>   @RequestMapping("/hello")
>>>   public ModelAndView hello(){
>>>     ModelAndView mav=new ModelAndView();
>>>     mav.setViewNmae("hello");
>>>     return mav;
>>>   }
>>>   @RequestMapping("/hello")
>>>   public String hello(){
>>>     return "hello";
>>>   }
>>> }
>>>```
>- View ์ด๋ฆ ์๋ ์ง์ 
>>- RequestToViewNameTranslator๋ฅผ ์ด์ฉํ์ฌ URL๋ก ๋ถํฐ view์ด๋ฆ์ ๊ฒฐ์ 
>>- ์๋ ์ง์  ์ ํ
>>>- return type์ด Model์ด๋ Map์ธ ๊ฒฝ์ฐ
>>>- return type์ด void์ด๋ฉด์ ServletResponse๋ HttpServletResponse ํ์์ parameter๊ฐ ์๋ ๊ฒฝ์ฐ
>>>```java
>>> @Controller
>>> public class HomeController {
>>>   @RequestMapping("/hello") // hello๊ฐ view ์ด๋ฆ์ด ๋จ
>>>   public Map<String, Object> hello(){
>>>     Map<String, Object> model=new HashMap<String, Object>();
>>>     return model;
>>>   }
>>> }
>>>```
>- redirect view
>>- View ์ด๋ฆ์ "redirect:" ์ ๋์ด๋ฅผ ๋ถ์ด๋ฉด ์ง์ ํ ํ์ด์ง๋ก ๋ฆฌ๋ค์ด๋ํธ
>>>```java
>>> @Controller
>>> public class HomeController {
>>>   @RequestMapping("/hello")
>>>   public Map<String, Object> hello(){
>>>     return "redirect:index";
>>>   }
>>> }
>>>```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

>## Model
>- View์ ์ ๋ฌํ๋ ๋ฐ์ดํฐ
>>- @RequestMapping annotation์ด ์ ์ฉ๋ method์ Map, Model, ModelMap
>>> ```java
>>> @Controller
>>> public class HomeController {
>>>   @RequestMapping("/hello")
>>>   public String hello(Map model){
>>>   //public String hello(ModelMap model){
>>>   //public String hello(Model model){
>>>     model.put("msg", "์ด์์ค์ธ์");
>>>     return "hello";
>>>   }
>>> }
>>> ```
>>>- Model Interface ์ฃผ์ method
>>>>- Model addAttribute(String name, Object value);
>>>>- Model addAttribute(Object value);
>>>>- Model addAllAttributes(Collection<?> values);
>>>>- Model addAllAttributes(Map<String, ?> attributes);
>>>>- Model mergeAttributes(Map<String, ?> attributes);
>>>>- boolean containsAttribute(String name);
>>- @RequestMapping method๊ฐ returnํ๋ ModelAndView
>>>- Controller์์ ์ฒ๋ฆฌ๊ฒฐ๊ณผ๋ฅผ ๋ณด์ฌ์ค view์ view์ ์ ๋ฌํ  ๊ฐ(model)์ ์ ์ฅํ๋ ์ฉ๋๋ก ์ฌ์ฉ
>>>>```java
>>>> @Controller
>>>> public class HomeController {
>>>>   @RequestMapping("/hello")
>>>>   public ModelAndView hello(){
>>>>     ModelAndView mav=new ModelAndView();
>>>>     mav.setViewName("hello");
>>>>     mav.addObject("msg", "์ด์์ค์ธ์");
>>>>     return mav;
>>>>   }
>>>> }
>>>>```
>>- @ModelAttribute annotation์ด ์ ์ฉ๋ method๊ฐ return ํ ๊ฐ์ฒด
>>>- @RequestMapping annotation์ด ์ ์ฉ๋์ง ์์ ๋ณ๋ method๋ก ๋ชจ๋ธ์ด ์ถ๊ฐ๋  ๊ฐ์ฒด๋ฅผ ์์ฑ
>>>> ```java
>>>> @Controller
>>>> public class HomeController {
>>>>   @ModelAttribute("modelmsg")
>>>>   public String msg() {
>>>>     return "bye";
>>>>   }
>>>>   
>>>>   @RequestMapping("/hello")
>>>>   public String hello(Map model){
>>>>     model.put("msg", "์ด์์ค์ธ์");
>>>>     return "hello";
>>>>   }
>>>> }
>>>> ```
>>>> ```html
>>>> <div align="center">
>>>> <h3>hello</h3>
>>>> ${msg}<br>
>>>> ${modelmsg}<br>
>>>> <a href="${root}/user/regist">ํ์๊ฐ์</a>
>>>> </div>
>>>> ```
>- ์์ฒญ URL ๋งค์นญ
>>- ์ ์ฒด ๊ฒฝ๋ก์ Servlet ๊ธฐ๋ฐ ๊ฒฝ๋ก ๋งค์นญ
>>>- DispatcherServlet์ DefaultAnnotationHandlerMapping Class๋ฅผ ๊ธฐ๋ณธ์ผ๋ก HandlerMapping ๊ตฌํ์ฒด๋ก ์ฌ์ฉ
>>>- Default๋ก Context๋ด์ ๊ฒฝ๋ก๊ฐ ์๋ Servlet ๊ฒฝ๋ก๋ฅผ ์ ์ธํ ๋๋จธ์ง ๊ฒฝ๋ก์ ๋ํด mapping
>>>```xml
>>><servlet>
>>>  <servlet-name>dispatcher</servlet-name>
>>>  <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
>>>  <load-on-startup>1</load-on-startup>
>>></servlet>
>>><servlet-mapping>
>>>  <servlet-name>dispatcher</servlet-name>
>>>  <url-pattern>*.html</url-pattern>
>>>  <url-pattern>/product/*</url-pattern>
>>></servlet-mapping>
>>>```
>>- Servlet ๊ธฐ๋ฐ ๊ฒฝ๋ก ๋งค์นญ
>>>- Servlet ๊ฒฝ๋ก๋ฅผ ํฌํจํ ์ ์ฒด ๊ฒฝ๋ก๋ฅผ ์ด์ฉํด์ ๋งค์นญํ๋ ค๋ ๊ฒฝ์ฐ
>>>- @RequestMapping("/user/regist")
>>>>```xml
>>>><bean class="org.springframework.web.servlet.mvc.annotation.DefaultAnnotationHandlerMapping">
>>>>  <property name="alwaysUseFullPath" value="true" />
>>>></bean>
>>>>
>>>><bean class="org.springframework.web.servlet.mvc.annotation.AnnotationMethodHandlerAdapter">
>>>>  <property name="alwaysUseFullPath" value="true" />
>>>></bean>
>>>>```
>>- @PathVariable annotation์ ์ด์ฉํ URI ํํ๋ฆฟ
>>>- RESTful ๋ฐฉ์
>>>>- **http**://localhost/users/troment
>>>>- **http**://localhost/product/
>>>>- **http**://localhost/forum/board/10
>>>- @RequestMapping Annotation ๊ฐ์ผ๋ก {ํํ๋ฆฟ๋ณ์}๋ฅผ ์ฌ์ฉ
>>>- @PathVariable Annotation์ ์ด์ฉํด์ {ํํ๋ฆฟ๋ณ์}์ ๋์ผํ ์ด๋ฆ์ ๊ฐ๋ parameter๋ฅผ ์ถ๊ฐ
>>>>```java
>>>> @Controller
>>>> public class BoardViewController {
>>>>   @RequestMapping("/{id}/board/{num}")
>>>>   public String view(@PathVariable String id, @PathVariable int num, Model model){
>>>>     Board board=boardService.getBoard(id, num);
>>>>     return "view";
>>>>   }
>>>> }
>>>>```
>>>>```java
>>>> @Controller
>>>> @RequestMapping("/{id}")
>>>> public class BoardViewController {
>>>>   @RequestMapping("/board/{num}")
>>>>   public String view(@PathVariable String id, @PathVariable int num, Model model){
>>>>     Board board=boardService.getBoard(id, num);
>>>>     return "view";
>>>>   }
>>>> }
>>>>```
>>>- @RequestMapping Annotation์ ์ถ๊ฐ์ค์  ๋ฐฉ๋ฒ
>>>>- Ant ์คํ์ผ์ URIํจํด ์ง์
>>>>>- ? : ํ๋์ ๋ฌธ์์ด๊ณผ ๋์น
>>>>>- * : ํ๋ ์ด์์ ๋ฌธ์์ด๊ณผ ๋์น
>>>>>- ** : ํ๋ ์ด์์ ๋๋ ํ ๋ฆฌ์ ๋์น
>>>>>```java
>>>>>@RequestMapping("/member/*.do")
>>>>>@RequestMapping("/*/board/{num}")
>>>>>```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

>## Spring Web Application์ ๋์์์
>1. ์น ์ดํ๋ฆฌ์ผ์ด์์ด ์คํ๋๋ฉด WAS(Tomcat)์ ์ํด web.xml์ด ๋ก๋ฉ
>2. web.xml์ ๋ฑ๋ก๋์ด ์๋ ContextLoaderListener (Java Class)๊ฐ ์์ฑ๋๊ณ  ContextLoaderListener class๋ ServletContextListener interface๋ฅผ ๊ตฌํํ๊ณ  ์์ผ๋ฉฐ, ApplicationContext๋ฅผ ์์ฑํ๋ ์ญํ ์ ์ํ
>3. ์์ฑ๋ ContextLoaderListener๋ root-context.xml์ ๋ก๋ฉ
>4. root-context.xml์ ๋ฑ๋ก๋์ด ์๋ ์คํ๋ง ์ปจํ์ด๋๊ฐ ๊ตฌ๋๋์ด ๊ฐ๋ฐ์๊ฐ ์์ฑํ ๋น์ง๋์ค ๋ก์ง(Service)์ ๋ํ ๋ถ๋ถ๊ณผ DAO, VO ๊ฐ์ฒด๋ค์ด ์์ฑ
>5. ํด๋ผ์ด์ธํธ๋ก๋ถํฐ request
>6. DispatcherServlet์ด ์์ฑ๋๋ฉฐ FrontController์ ์ญํ ์ ์ํ
>>- ํด๋ผ์ด์ธํธ์ ์์ฒญ์ ๋ถ์ํ์ฌ ์๋ง์ ์ปจํธ๋กค๋ฌ์๊ฒ ์ ๋ฌํ๊ณ  ์๋ต์ ๋ฐ์ ์์ฒญ์ ๋ฐ๋ฅธ ์๋ต์ ์ด๋ป๊ฒ ํ  ์ง ๊ฒฐ์ 
>>- HandlerMapping, ViewResolver Class๋ผ๊ณ  ๋ถ๋ฆ
>7. DispatcherServlet์ servlet-context.xml์ ๋ก๋ฉ
>8. ๋๋ฒ์งธ ์คํ๋ง ์ปจํ์ด๋๊ฐ ๊ตฌ๋๋๋ฉฐ ์๋ต์ ๋ง๋ ์ปจํธ๋กค๋ฌ๋ค์ด ๋์
>>- ์ฒซ๋ฒ์จฐ ์คํ๋ง ์ปจํ์ด๋๊ฐ ๊ตฌ๋๋๋ฉด์ ์์ฑ๋ Service, DAO, VO ํด๋์ค๋ค๊ณผ ํ์ํ์ฌ ์์์ฒ๋ฆฌ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

>## FileUpload
>- ๊ตฌํ๋ฐฉ๋ฒ
>>- pom.xml
>> ```xml
>> <dependency>
>>   <groupId>commons-fileupload</groupId>
>>   <artifactId>commons-fileupload</artifactId>
>>   <version>1.3.3</version>
>> </dependency>
>> ```
>>- servlet-context.xml
>> ```xml
>> <beans:bean id="multipartResolver" class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
>>   <beans:property name="defaultEncoding" value="UTF-8"/>
>>   <!-- ์ต๋ ์๋ก๋ ๊ฐ๋ฅํ ํ์ผ์ ๋ฐ์ดํธ ํฌ๊ธฐ -->
>>   <beans:property name="maxUploadSize" value="52428800"/> 
>>   <!-- ๋์คํฌ์ ์์ ํ์ผ์ ์์ฑํ๊ธฐ ์ ์ ๋ฉ๋ชจ๋ฆฌ์ ๋ณด๊ดํ  ์ ์๋ ์ต๋ ๋ฐ์ดํธ ํฌ๊ธฐ -->
>>   <beans:property name="maxInMemorySize" value="1048576"/>
>> </beans:bean>
>> ``` 
>>- write.jsp
>> ```html
>> <form method="post" enctype="multipart/form-data" action="">
>>   <label for="title">์ ๋ชฉ:</label>
>>   <input type="text" id="title" name="title">
>>   <label for="content">๋ด์ฉ:</label>
>>   <input type="text" id="content" name="content">
>>   <label for="file">ํ์ผ:</label>
>>   <input type="file" name="upfile" multiple="multiple">
>>   <button type="button">๊ธ์์ฑ</button>
>>   <button type="reset">์ด๊ธฐํ</button>
>> </form>
>> ```
>>- FileInfoDto.java
>> ```java
>> public class FileInfoDto {
>>   private String isbn;
>>   private String saveFolder;
>>   private String originFile;
>>   private String saveFile;
>> }
>> ```
>>- BookDto.java
>> ```java
>> public class BookDto {
>>   private int isbn;
>>   private String title;
>>   private String content;
>>   private String regtime;
>>   private List<FileInfoDto> fileInfos;
>> }
>> ```
>>- BookServiceImpl.java
>> ```java
>> @Override
>> @Transactional
>> public void writeBook(BookDto bookDto) throws Exception {
>>   if(bookDto.getIsbn()==null || bookDto.getContent()==null) throw new Exception();
>>   BookMapper bookMapper=sqlSession.getMapper(BookMapper.class);
>>   bookMapper.writeBook(bookDto);
>>   bookMapper.fileRegister(bookDto);
>> }
>> ```
>>- BookController.java
>> ```java
>> @RequestMapping(value="/write", method=RequestMethod.POST)
>> public String write(BookDto bookDto, @RequestParam("upfile" MultipartFile[] files), ... ) {
>>   String realPath=servletContext.getRealPath("/upload");
>>   String today=new SimpleDateFormant("yyMMdd").format(new Date());
>>   String saveFolder=realPath.File.separator+today;
>>   File folder=new File(saveFolder);
>>   if(!folder.exists()) folder.mkdirs();
>>   List<FileInfoDto> fileInfos=new ArrayList<FileInfoDto>();
>>   for(MultipartFile mfile : files) {
>>     FileInfoDto fileInfoDto=new FileInfoDto();
>>     String originalFileName=mfile.getOriginalFilename();
>>     if(!originalFileName.isEmpty()) {
>>       String saveFileName=UUID.randomUUID().toString()+originalFileName.substring(originalFileName.lastIndexOf('.'));
>>       fileInfoDto.setSaveFolder(today);
>>       fileInfoDto.setOriginFile(originalFileName);
>>       fileInfoDto.setSaveFile(saveFileName);
>>       mfil.transferTo(new File(folder, saveFileName));
>>     }
>>     fileInfos.add(fileInfoDto);
>>   }
>>   bookDto.setFileInfos(fileInfos);
>>   try {
>>     bookService.writeBook(bookDto);
>>     return "book/writesuccess";
>>   } catch (Exception e) {
>>     model.addAttribute("msg", "์์ฑ์คํจ");  
>>     return "error/error";
>>   }
>> }
>> 
>> ```
>>- book.xml
>> ```xml
>> <resultMap type="BookDto" id="bookList">
>>   <result property="isbn" column="isbn" />
>>   <result property="title" column="title" />
>>   <result property="content" column="content" />
>>   <result property="regtime" column="regtime" />
>>   <collection property="fileInfos" column="isbn" javaType="List" ofType="FileInfoDto" select="fileInfoList" />
>> </resultMap>
>> 
>> <insert id="writeBook" parameterType="BookDto">
>>   insert into book {isbn, title, content, regtime} values(${isbn}, ${title}, ${content}, now())
>>   <selectKey resultType="int" keyProperty="isbn" order"AFTER">
>>     SELECT LAST_INSERT_ID()
>>   </selectKey>
>> </insert>
>> <insert id="fileRegister" parameterType="BookDto">
>>   insert into file_info (isbn, savefolder, orginfile, savefile) values
>>   <foreach collection="fileInfos" item="fileinfo" separator=" , ">
>>     (#{isbn}, #{fileinfo.saveFolder}, #{fileinfo.originFile}, #{fileinfo.saveFile})
>>   </foreach>
>> </insert>
>> <select id="listBook" parameterType="map" resultMap="bookList">
>>   select isbn, title, content, regtime from book
>>   <if test="word != null and word != ''">
>>     <if test="key == 'title'">
>>       where title like concat('%', #{word}, '%')
>>     </if>
>>     <if test="key != 'title'">
>>       where title like concat('%', #{word}, '%')
>>     </if>
>>   </if>
>>   order by isbn desc limit #{start}, #{spp}
>> </select>
>> <select id="fileInfoList" resultType="FileInfoDto">
>>   select savefolder, originfile, savefile from file_info where isbn=#{isbn}
>> </select>
>> ```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

>## FileDownload
>- ๊ตฌํ๋ฐฉ๋ฒ
>>- list.jsp
>>```html
>><script type="text/javascript">
>>$('.filedown).click(function() {
>>  $(document).find('[name="sfolder"').val$(this).attr('sfolder'));
>>  $(document).find('[name="ofile"').val$(this).attr('ofile'));
>>  $(document).find('[name="sfile"').val$(this).attr('sfile'));
>>  $('#downform').attr('action', '${root}/book/download').attr('method','get').submit();
>>});
>></script>
>>
>><ul>
>>  <c:forEach var="file" items="${book.fileInfos}">
>>  <li>${file.originFile} <a href="#" sfolder="${file.saveFolder}" sfile="${file.saveFile}" ofile="${file.originFile}">๋ค์ด๋ก๋</a>
>>  </c:forEach>
>></ul>
>>```
>>- servlet-context.xml
>>```xml
>><beans:bean id="fileDownLoadView" class="com.user.book.controller.FileDownLoadView" />
>><beans:bean id="fileViewResolver" class="org.springframework.web.servlet.view.BeanNameViewResolver">
>>  <beans:property name="order" value="0" />
>></beans:bean>
>>```
>>- BookController.java
>>```java
>>@RequestMapping(value="/download", method=RequestMethod.GET)
>>public ModelAndView downloadFile(@RequestParam("sfolder") String sfolder, @RequestParam("ofile") String ofile, @RequestParam("sfile") String sfile, HttpSession session){
>>  MemberDto memberDto=(MemberDto) session.getAttribute("userinfo");
>>  if(memberDto!=null) {
>>    Map<String, Object> fileInfo=new HashMap<STring, Object>();
>>    fileInfo.put("sfolder", sfolder);
>>    fileInfo.put("ofile", ofile);
>>    fileInfo.put("sfile", sfile);
>>    return new ModelAndView("fileDownLoadView", "downloadFile", fileInfo);
>>  } else {
>>    return new ModelAndView("redirect:/");
>>  }
>>}
>>```
>>- FileDownLoadView.java
>>```java
>>response.setContentType(getContentType());
>>response.setContentLength((int) file.length());
>>
>>String header=request.getHeader("User-Agent");
>>boolean isIE=header.indexOf("MSIE")>-1 || header.indexOf("Trident")>-1;
>>String fileName=null;
>>if(isIE) fileName=URLEncoder.encode(originalFile, "UTF-8").replaceAll("\\+", "%20");
>>else     fileName=new String(originalFile.getBytes("UTF-8"), "ISO-8859-1");
>>
>>response.setHeader("Content-Disposition", "attachment; filename=\""+fileName+"\";");
>>response.setHeader("Content-Transfer-Encoding", "binary");
>>OutputStream out=response.getOutputStream();
>>FileInputStream fis=null;
>>try {
>>  fis=new FileInputStream(file);
>>  FileCopyUtils.copy(fis, out);
>>```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

>## Interceptor
>- HandlerInterceptor
>>- Controller๊ฐ ์์ฒญ์ ์ฒ๋ฆฌํ๊ธฐ ์ /ํ ์ฒ๋ฆฌ๊ฐ๋ฅ
>>- ๋ก๊น, ๋ชจ๋ํฐ๋ง ์ ๋ณด ์์ง, ์ ๊ทผ ์ ์ด ์ฒ๋ฆฌ ๋ฑ ์ค์  ๋น์ง๋์ค ๋ก์ง๊ณผ๋ ๋ถ๋ฆฌ๋์ด ์ฒ๋ฆฌํด์ผ ํ๋ ๊ธฐ๋ฅ ์ฒ๋ฆฌ
>>- interceptor๋ฅผ ์ฌ๋ฌ ๊ฐ ์ค์ ํ  ์ ์์(์์์ ์ฃผ์ํด์ผ ํจ)
>- HandlerInterceptor ์ ๊ณต method
>>- boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler)
>>>- false๋ฅผ ๋ฐํํ๋ฉด request๋ฅผ ๋ฐ๋ก ์ข๋ฃ
>>- void postHandle(HttpServletRequest request, HttpServletResponse response, Object handler, ModelAndView modelAndView)
>>>- Controller ์ํ ํ ํธ์ถ
>>- void afterCompletion(HttpServletRequest request, HttpServletResponse response, Object handler, Exception ex)
>>>- view๋ฅผ ํตํด ํด๋ผ์ด์ธํธ์ ์๋ต์ ์ ์กํ ๋ค ์คํ
>>>- ์์ธ๊ฐ ๋ฐ์ํด๋ ์คํ
>- Interceptor ํธ์ถ ์์
>>```xml
>><!-- servlet-context.xml -->
>><mvc:interceptors>
>>  <mvc:interceptor>
>>    <mvc:mapping path="/*.html"/>
>>    <bean class="com.test.hello.aInterceptor"/>
>>  </mvc:interceptor>
>>  <mvc:interceptor>
>>    <mvc:mapping path="/*.html"/>
>>    <bean class="com.test.hello.bInterceptor"/>
>>  </mvc:interceptor>
>>  <mvc:interceptor>
>>    <mvc:mapping path="/*.html"/>
>>    <bean class="com.test.hello.cInterceptor"/>
>>  </mvc:interceptor>
>></mvc:interceptors>
>>```
>>![Interceptor_Order](./imgs/Interceptor_Order.PNG)
>- ๊ตฌํ๋ฐฉ๋ฒ
>>- LoggingInterceptor.java
>>```java
>>public class LoggingInterceptor implements HandlerInterceptor {
>>  @Override
>>  public boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler) throws Exception {
>>    System.out.println("preHandle");
>>    return true;
>>  }
>>  @Override
>>  public void postHandle(HttpServletRequest request, HttpServletResponse response, Object handler, ModelAndView modelAndView) throws Exception {
>>    System.out.println("postHandle");
>>  }
>>  @Override
>>  public void afterCompletion(HttpServletRequest request, HttpServletResponse response, Object handler, Exception ex) throws Exception {
>>    System.out.println("afterCompletion");
>>  }
>>}
>>```
>>- servlet-context.xml
>>```xml
>><mvc:interceptors>
>>  <mvc:interceptor>
>>    <mvc:mapping path="/*.html"/>
>>    <bean class="com.test.hello.LoggingInterceptor"/>
>>  </mvc:interceptor>
>>  <mvc:interceptor>
>>    <mvc:mapping path="/*.html"/>
>>    <bean class="com.test.hello.EtcInterceptor"/>
>>  </mvc:interceptor>
>></mvc:interceptors>
>>```
>- ๋ก๊ทธ์ธ ์ธ์ ์ฒดํฌ ์์
>>- servlet-context.xml
>>```xml
>><beans:bean id="confirm" class="com.test.interceptor.ConfirmInterceptor" />
>>
>><interceptors>
>>  <interceptor>
>>    <mapping path="/user/write" />
>>    <mapping path="/user/modify" />
>>    <mapping path="/user/delete" />
>>    <beans:ref bean="confirm" />
>>  </interceptor>
>></interceptors>
>>```
>>- ConfirmInterceptor.java
>>```java
>>public class ConfirmInterceptor implements HandlerInterceptorAdapter {
>>  @Override
>>  public boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler) throws Exception {
>>    HttpSession session=request.getSession();
>>    MemberDto memberDto=(MemberDto) session.getAttribute("userinfo");
>>    if(memberDto==null) {
>>      response.sendRedirect(request.getContextPath());
>>      return false;  
>>    }
>>    return true;
>>  }
>>}
>>```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

>## MyBatis
>- Java Object์ SQL๋ฌธ ์ฌ์ด์ ์๋ Mapping ๊ธฐ๋ฅ์ ์ง์ํ๋ ORM Framework
>>- SQL์ ๋ณ๋์ ํ์ผ๋ก ๋ถ๋ฆฌํ์ฌ ๊ด๋ฆฌํ  ์ ์์
>>- SQL ๊ณผ Object ์ฌ์ด์ parameter mapping ์์์ ์๋์ผ๋ก ํจ
>>- Hibernate๋ JPA์ฒ๋ผ ์๋ก์ด DB ํ๋ก๊ทธ๋๋ฐ ํจ๋ฌ๋ค์์ ๋ฐฐ์์ผ ํ๋ ๋ถ๋ด์์ด, ์ต์ํ SQL์ ๊ทธ๋๋ก ์ด์ฉํ๋ฉด์ JDBC ์ฝ๋ ์์ฑ์ ๋ถํธํจ์ ์ ๊ฑฐํด ์ฃผ๊ณ , ๋๋ฉ์ธ ๊ฐ์ฒด๋ VO ๊ฐ์ฒด๋ฅผ ์ค์ฌ์ผ๋ก ๊ฐ๋ฐํ  ์ ์์
>- ํน์ง
>>- ์ฌ์ด ์ ๊ทผ์ฑ๊ณผ ์ฝ๋์ ๊ฐ๊ฒฐํจ
>>>- ๊ฐ์ฅ ๊ฐ๋จํ ์์์ฑ ํ๋ ์์ํฌ
>>>- XMLํํ๋ก ์์ ๋ JDBC์ฝ๋๋ผ ์๊ฐํ ๋งํผ JDBC์ ๋ชจ๋  ๊ธฐ๋ฅ์ ๋๋ถ๋ถ ์ ๊ณต
>>>- ๋ณต์กํ JDBC์ฝ๋๋ฅผ ๊ฑท์ด๋ด์ด ๊น๋ํ ์์ค์ฝ๋๋ฅผ ์ ์งํ  ์ ์์
>>>- ์๋์ ์ธ parameter ์ค์ ๊ณผ Query ๊ฒฐ๊ณผ์ ๋ํ mapping ๊ตฌ๋ฌธ์ ์ ๊ฑฐ
>>- SQL ๋ฌธ๊ณผ ํ๋ก๊ทธ๋๋ฐ ์ฝ๋์ ๋ถ๋ฆฌ
>>>- SQL ๋ณ๊ฒฝ์ด ์์ ๋๋ง๋ค ์๋ฐ ์ฝ๋๋ฅผ ์์ ํ๊ฑฐ๋ ์ปดํ์ผ ํ์ง ์์๋ ๋จ
>>>- SQL ์์ฑ๊ณผ ๊ด๋ฆฌ ๋๋ ๊ฒํ ๋ฅผ DBA์ ๊ฐ์ ๊ฐ๋ฐ์๊ฐ ์๋ ๋ค๋ฅธ ์ฌ๋์๊ฒ ๋งก๊ธธ ์ ์์
>- MyBatis 3 ์ ์ฃผ์ Component
>>ํ์ผ|์ค๋ช
>>:--|:--
>>MyBatis ์ค์ ํ์ผ (sqlMapConfig.xml)|db์ ์ ์ ์ฃผ์ ์ ๋ณด๋ ๊ฐ์ฒด์ alias, Mapping ํ์ผ์ ๊ฒฝ๋ก ๋ฑ์ ๊ณ ์ ๋ ํ๊ฒฝ ์ ๋ณด๋ฅผ ์ค์ 
>>SqlSessionFactoryBuilder|MyBatis ์ค์  ํ์ผ์ ๋ฐํ์ผ๋ก SqlSessionFactory ๋ฅผ ์์ฑ
>>SqlSessionFactory|SqlSession ์ ์์ฑ
>>SqlSession|ํต์ฌ์ ์ธ ์ญํ ์ ํ๋ Class๋ก SQL ์คํ์ด๋ ํธ๋์ญ์ ๊ด๋ฆฌ๋ฅผ ์คํ
>>&nbsp;|SqlSession ์ค๋ธ์ ํธ๋ ์ฐ๋ ๋์ ์์ ํ์ง ์์ผ๋ฏ๋ก ์ฐ๋ ๋๋ง๋ค ํ์์ ๋ฐ๋ผ ์์ฑํด์ผํจ
>>mappingํ์ผ (member.xml)|SQL ๋ฌธ๊ณผ ORMapping(๊ฐ์ฒด๊ด๊ณ๋งคํ)์ ์ค์ 
>- MyBatis-Spring ์ ์ฃผ์ Component
>>ํ์ผ|์ค๋ช
>>:--|:--
>>MyBatis ์ค์ ํ์ผ (sqlMapConfig.xml)|Dto ๊ฐ์ฒด์ ์ ๋ณด๋ฅผ ์ค์  (Alias)
>>SqlSessionFactoryBean|MyBatis ์ค์  ํ์ผ์ ๋ฐํ์ผ๋ก SqlSessionFactory๋ฅผ ์์ฑ
>>&nbsp;|Spring Bean์ผ๋ก ๋ฑ๋กํด์ผ ํจ
>>SqlSessionTemplate|ํต์ฌ์ ์ธ ์ญํ ์ ํ๋ ํด๋์ค๋ก์ SQL ์คํ์ด๋ ํธ๋์ญ์ ๊ด๋ฆฌ๋ฅผ ์คํ
>>&nbsp;|SqlSession interface๋ฅผ ๊ตฌํํ๋ฉฐ, ์ฐ๋ ๋์ ์์ ํจ
>>&nbsp;|Spring Bean์ผ๋ก ๋ฑ๋กํด์ผ ํจ
>>mappring ํ์ผ (member.xml)|SQL๋ฌธ๊ณผ ORMapping(๊ฐ์ฒด๊ด๊ณ๋งคํ)์ ์ค์ 
>>Spring Bean ์ค์ ํ์ผ (beans.xml)|SqlSessionFactoryBean์ Bean์ ๋ฑ๋กํ  ๋ DataSource ์ ๋ณด์ MyBatis Config ํ์ผ ์ ๋ณด, Mapping ํ์ผ์ ์ ๋ณด๋ฅผ ํจ๊ป ์ค์ 
>>&nbsp;|SqlSessionTemplate๋ฅผ Bean์ผ๋ก ๋ฑ๋ก

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### Mapper Interface
>- mapping ํ์ผ์ ๊ธฐ์ฌ๋ SQL์ ํธ์ถํ๊ธฐ ์ํ Interface
>>- SQL์ ํธ์ถํ๋ ํ๋ก๊ทธ๋จ์ Type Safe ํ๊ฒ ๊ธฐ์ ํ๊ธฐ ์ํด MyBatis 3.x ๋ถํฐ ๋ฑ์ฅํจ
>>- Mapping ํ์ผ์ ์๋ SQL์ java interface๋ฅผ ํตํด ํธ์ถํ  ์ ์๋๋ก ํจ
>### MyBatis์ Spring์ ์ฐ๋
>- ๊ฐ์
>>- MyBatis๋ฅผ Standalone ํํ๋ก ์ฌ์ฉํ๋ ๊ฒฝ์ฐ, SqlSessionFactory ๊ฐ์ฒด๋ฅผ ์ง์  ์ฌ์ฉํจ
>>- ์คํ๋ง์ ์ฌ์ฉํ๋ ๊ฒฝ์ฐ ์คํ๋ง ์ปจํ์ด๋์ MyBatis ๊ด๋ จ ๋น์ ๋ฑ๋กํ์ฌ ์ฌ์ฉ
>>- ์คํ๋ง์์ ์ ๊ณตํ๋ ํธ๋์ญ์ ๊ธฐ๋ฅ์ ์ฌ์ฉํ๋ฉด ์์ฝ๊ฒ ํธ๋์ญ์ ์ฒ๋ฆฌ๊ฐ๋ฅ
>>- ์ฐ๋ํ๊ธฐ ์ํด์ ์ฐ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๊ฐ ํ์
>>>```xml
>>><dependency>
>>>  <groupId>org.mybatis</groupId>
>>>  <artifactId>mybatis-spring</artifactId>
>>>  <version>2.0.2</version>
>>></dependency>
>>>```
>- DataSource
>>- ์คํ๋ง์์ DataSource๋ฅผ ๊ด๋ฆฌํ๋ฏ๋ก MyBatis ์ค์ ํ์ผ์์๋ ์ผ๋ถ ์ค์ ์ ์๋ตํจ
>>- application-context.xml ์ DataSource ์ค์ 
>>- DataSource๋ dataSource ์์ด๋๋ฅผ ๊ฐ์ง ๋น์ผ๋ก ๋ฐ์ดํฐ๋ฒ ์ด์ค ์ฐ๊ฒฐ์ ๋ณด๋ฅผ ๊ฐ์ง ๊ฐ์ฒด์
>>- MyBatis์ ์คํ๋ง์ ์ฐ๋ํ๋ฉด db ์ค์ ๊ณผ ํธ๋์ญ์ ์ฒ๋ฆฌ๋ ์คํ๋ง์์ ๊ด๋ฆฌํจ
>>>```xml
>>><!-- ์ผ๋ฐ ์ค์  -->
>>><bean id="dataSource" class="org.springframework.jdbc.datasource.SimpleDriverDataSource" destroy-method="close">
>>>  <property name="driverClass" value="com.mysql.cj.jdbc.Driver" />
>>>  <property name="url" value="jdbc:mysql://127.0.0.1:3306/testdb?serverTimezone=UTC&amp;useUniCode=yes&amp;characterEncoding=UTF-8" />
>>>  <property name="username" value="id" />
>>>  <property name="password" value="pw" />
>>></bean>
>>>
>>><!-- ConnectionPool ์ค์  -->
>>><bean id="dataSource" class="org.springframework.jndi.JndiObjectFactoryBean">
>>>  <property name="jndiName" value="java:comp/env/jdbc/testdb" />
>>></bean>
>>>```
>- ํธ๋์ญ์ ๊ด๋ฆฌ์ ์ค์ 
>>- transactionManager ์์ด๋๋ฅผ ๊ฐ์ง ๋น์ ํธ๋์ญ์์ ๊ด๋ฆฌํ๋ ๊ฐ์ฒด์
>>- MyBatis๋ JDBC๋ฅผ ๊ทธ๋๋ก ์ฌ์ฉํ๊ธฐ ๋๋ฌธ์ DataSourceTransactionManager ํ์์ ๋น์ ์ฌ์ฉํจ
>>- tx:annotation-driven ์์๋ ํธ๋์ญ์ ๊ด๋ฆฌ๋ฐฉ๋ฒ์ ์ด๋ธํ์ด์์ผ๋ก ์ ์ธํ๋๋ก ์ค์ 
>>- ์คํ๋ง์ ๋ฉ์๋๋ ํด๋์ค์ @Transactional ์ด ์ ์ธ๋์ด ์์ผ๋ฉด AOP๋ฅผ ํตํด ํธ๋์ญ์์ ์ฒ๋ฆฌํจ
>>>```xml
>>><!-- ํธ๋์ญ์ ๊ด๋ฆฌ์ ์ค์  -->
>>><bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
>>>  <property name="dataSource" ref="dataSource" />
>>></bean>
>>>
>>><!-- ์ด๋ธํ์ด์ ๊ธฐ๋ฐ ํธ๋์ญ์ ์ค์  -->
>>><tx:annotation-driven transaction-manager="transactionManager" />
>>>```
>- SqlSessionFactoryBean ์ค์ 
>>- MyBatis ์ ํ๋ฆฌ์ผ์ด์์ SqlSessionFactory ๋ฅผ ์ค์ฌ์ผ๋ก ์ํ๋จ
>>- ์คํ๋ง์์ SqlSessionFactory ๊ฐ์ฒด๋ฅผ ์์ฑํ๊ธฐ ์ํด์๋ SqlSessionFactoryBean ์ ๋น์ผ๋ก ๋ฑ๋กํด์ผ ํจ
>>- SqlSessionFactoryBean ์ ๋น์ผ๋ก ๋ฑ๋กํ  ๋, ์ฌ์ฉํ  DataSource ์ mybatis ์ค์ ํ์ผ ์ ๋ณด๊ฐ ํ์ํจ
>>>```xml
>>><bean id="sqlSessionFactoryBean" class="org.mybatis.spring.SqlSessionFactoryBean">
>>>  <property name="dataSource" ref="dataSource" />
>>>  <property name="configLocation" value="classpath:com/user/config/mybatis/mybatis-config.xml" />
>>>  <property name="mapperLocation">
>>>    <list>
>>>      <value>classpath:com/user/config/mybatis/admin_board.xml</value>
>>>      <value>classpath:com/user/config/mybatis/admin_member.xml</value>
>>>    </list>
>>>  </perperty>
>>></bean>
>>>```
>- mapper ๋น ๋ฑ๋ก
>>- Mapper ์ธํฐํ์ด์ค๋ฅผ ์ฌ์ฉํ๊ธฐ ์ํด ์ค์บ๋๋ฅผ ์ฌ์ฉํ์ฌ ์๋์ผ๋ก ๋ฑ๋กํ๊ฑฐ๋, ์ง์  ๋น์ผ๋ก ๋ฑ๋ก
>>- mapperScannerConfigurer ์ ์ค์ ํ๋ฉด, Mapper ์ธํฐํ์ด์ค๋ฅผ ์๋์ผ๋ก ๊ฒ์ํ์ฌ ๋น์ผ๋ก ๋ฑ๋ก
>>>- basePackage ๋ก ํจํค์ง๋ ์ค์ ํ๋ฉด, ํด๋น ํจํค์ง ํ์์ ๋ชจ๋  ๋งคํผ ์ธํฐํ์ด์ค๊ฐ ์๋์ผ๋ก ๋ฑ๋ก๋จ
>>- MapperFactoryBean ํด๋์ค๋ ๋งคํผ ์ธํฐํ์ด์ค๋ฅผ ์ง์  ๋ฑ๋กํ  ๋ ์ฌ์ฉํจ
>>>```xml
>>><!-- mapper scanner ์ฌ์ฉ -->
>>><bean id="mapperScannerConfigurer" class="org.mybatis.spring.mapper.MapperScannerConfigurer">
>>>  <property name="basePackage" value="com.test.user.mybatis.mapper">
>>></bean>
>>><!-- mapper interface ์ง์  ๋ฑ๋ก -->
>>><bean id="authorMapper" class="org.mybatis.spring.mapper.MapperFactoryBean">
>>>  <property name="mapperInterface" value="com.test.user.mybatis.mapper.AuthorMapper" />
>>>  <property name="sqlSessionFactory" ref="sqlSessionFactory" />
>>></bean>
>>>```
>- MyBatis Configuration
>>- ์คํ๋ง์ ์ฌ์ฉํ๋ฉด DB ์ ์์ ๋ณด ๋ฐ Mapper ๊ด๋ จ ์ค์ ์ ์คํ๋ง ๋น์ผ๋ก ๋ฑ๋กํ์ฌ ๊ด๋ฆฌํจ
>>- MyBatis ํ๊ฒฝ์ค์  ํ์ผ์๋ ์คํ๋ง์์ ๊ด๋ฆฌํ์ง ์๋ ์ผ๋ถ ์ ๋ณด๋ง ์ค์ ํจ
>>```xml
>><?xml version="1.0" encoding="UTF-8">
>><!DOCTYPE configuraion PUBLIC "-//mybatis.org//DTD Config 3.0//EN" "http://mybatis.org/dtd/mybatis-3-config.dtd">
>>
>><configuration>
>>  <typeAliases>
>>    <typeAlias alias="UserParameterDto" type="com.test.user.model.UserParameterDto" />
>>    <typeAlias alias="boardParameterDto" type="com.test.board.model.BoardParameterDto" />
>>  </typeAliases>
>></configuration>
>>```
>- ๋ฐ์ดํฐ ์ ๊ทผ ๊ฐ์ฒด ๊ตฌํ
>>- ๋ฐ์ดํฐ ์ ๊ทผ๊ฐ์ฒด๋ ํน์ ํ ๊ธฐ์ ์ ์ฌ์ฉํ์ฌ ๋ฐ์ดํฐ ์ ์ฅ์์ ์ ๊ทผํ๋ ๋ฐฉ์์ ๊ตฌํํ ๊ฐ์ฒด
>>- @Repository ๋ ๋ฐ์ดํฐ ์ ๊ทผ ๊ฐ์ฒด๋ฅผ ๋น์ผ๋ก ๋ฑ๋กํ๊ธฐ ์ํด ์ฌ์ฉํ๋ ์คํ๋ง์์ ์ ๊ณตํ๋ ์ด๋ธํ์ด์
>>- @Autowired ์ด๋ธํ์ด์์ ํตํด, ์ฌ์ฉํ๋ ค๋ Mapper ์ธํฐํ์ด์ค๋ฅผ ๋ฐ์ดํฐ ์ ๊ทผ๊ฐ์ฒด์ ์์กด๊ด๊ณ๋ฅผ ์ค์ ํจ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

## REST API

> OPEN API
>- ํ๋ก๊ทธ๋๋ฐ์์ ์ฌ์ฉํ  ์ ์๋๋ก ๊ฐ๋ฐฉ๋์ด ์๋ ์ํ์ ์ธํฐํ์ด์ค
>- ๊ด๊ณต์, ๊ณต๊ณต ๋ฐ์ดํฐ ํฌํธ, ๋ํ ํฌํธ ์ฌ์ดํธ๊ฐ ๊ฐ์ง๊ณ  ์๋ ๋ฐ์ดํฐ๋ฅผ ์ธ๋ถ ์์ฉ ํ๋ก๊ทธ๋จ์์ ์ฌ์ฉํ  ์ ์๋๋ก OPEN API๋ฅผ ์ ๊ณตํ๊ณ  ์์
>- OPEN API์ ํจ๊ป ๊ฑฐ๋ก ๋๋ ๊ธฐ์ ์ด REST์ด๋ฉฐ, ๋๋ถ๋ถ์ OPEN API๋ REST ๋ฐฉ์์ผ๋ก ์ง์
>### REST (Representational State Transfer)
>- URI๋ ํ๋์ ๊ณ ์ ํ ๋ฆฌ์์ค๋ฅผ ๋ํํ๋๋ก ์ค๊ณ๋๋ค๋ ๊ฐ๋์ ์ ์ก๋ฐฉ์์ ๊ฒฐํฉํ์ฌ ์ํ๋ ์์์ ์ง์ ํจ
>>- URI + GET/POST/PUT/DELETE
>- ์น์ ์ฅ์ ์ ์ต๋ํ ํ์ฉํ  ์ ์๋ ์ํคํ์ฒ(์ค๊ณ๊ตฌ์กฐ)๋ก์จ ์ฌ์ฉ
>>- HTTP URI๋ฅผ ํตํด ์ ์ดํ  ์์(Resource)๋ฅผ ๋ช์ํ๊ณ  HTTP Method(GET,POST,PUT,DELETE)๋ฅผ ํตํด ํด๋น ์์์ ์ ์ดํ๋ ๋ช๋ น์ ๋ด๋ฆฌ๋ ๋ฐฉ์์ ์ํคํ์ฒ
>- REST์ ๊ตฌ์ฑ
>>- ์์ (Resource) - URI
>>- ํ์ (Verb) - HTTP Method
>>- ํํ (Representations)
>- ๊ธฐ์กด ์๋น์ค์ REST ์๋น์ค์ ์ฐจ์ด์ 
>>- ๊ธฐ์กด ์๋น์ค: ์์ฒญ์ ๋ํ ์ฒ๋ฆฌ๋ฅผ ํ ํ ๊ฐ๊ณต๋ data๋ฅผ ์ด์ฉํ์ฌ ํน์  ํ๋ซํผ์ ์ ํฉํ ํํ์ View๋ก ๋ง๋ค์ด ๋ฐํ
>>- REST ์๋น์ค: data ์ฒ๋ฆฌ๋ง ํ๊ฑฐ๋, ์ฒ๋ฆฌ ํ ๋ฐํ๋ data๊ฐ ์๋ค๋ฉด JSON์ด๋ XML ํ์์ผ๋ก ์ ๋ฌํจ
>>>- View์ ๋ํด ์ ๊ฒฝ์ฐ์ง ์์๋ ๋๋ ์ฅ์ ์ผ๋ก OPEN API์์ ๋ง์ด ์ฌ์ฉ๋จ
>- ํน์ง
>>- ๊ธฐ์กด ์๋น์ค์ ๋ฌ๋ฆฌ ์๋ฒ๋ ์์ฒญ์ผ๋ก ๋ฐ์ ๋ฆฌ์์ค์ ๋ํด ์์ํ ๋ฐ์ดํฐ๋ง ์ ์กํจ
>>- ๊ธฐ์กด GET/POST ์ PUT/DELETE ๋ฐฉ์์ ์ถ๊ฐํ์ฌ ๋ฆฌ์์ค์ ๋ํ CRUD ์ฒ๋ฆฌ๋ฅผ ํ  ์ ์์
>>>- ์์|๊ธฐ์กด๋ฐฉ์|REST๋ฐฉ์|๋น๊ณ 
>>>   :--|:--|:--|:--
>>>   Create(Insert)|POST /write.do?id=abc|POST /blog/abc|๊ธ์ฐ๊ธฐ
>>>   Read(Select)|GET /view.do?id=abc&no=25|GET /blog/abc/25|๊ธ์ฝ๊ธฐ
>>>   Update(Update)|POST /modify.do?id=abc|PUT /blog/abc|๊ธ์์ 
>>>   Delete(Delete)|GET /delete.do?id=abc&no=25|DELETE /blog/abc/25|๊ธ์ญ์ 
>>- ๊ฐ์ฅ ํฐ ๋จ์ ์ผ๋ก ์ ํด์ง ํ์ค์ด ์์ด ์๋ฌต์ ์ธ ํ์ค๋ง ์ ํด์ ธ ์์
>>>- ํ์ดํ(-)์ ์ฌ์ฉ ๊ฐ๋ฅํ์ง๋ง ์ธ๋๋ฐ(_)๋ ์ฌ์ฉํ์ง ์์
>>>- ๋์๋ฌธ์ ๊ตฌ๋ถ์ ํ๊ธฐ ๋๋ฌธ์ ํน๋ณํ ๊ฒฝ์ฐ๋ฅผ ์ ์ธํ๊ณ  ๋๋ฌธ์ ์ฌ์ฉ์ ํ์ง์์
>>>- URI ๋ง์ง๋ง์ ์ฌ๋์(/)๋ฅผ ์ฌ์ฉํ์ง ์์
>>>- ์ฌ๋์(/)๋ก ๊ณ์ธต ๊ด๊ณ๋ฅผ ๋ํ๋
>>>- ํ์ฅ์๊ฐ ํฌํจ๋ ํ์ผ ์ด๋ฆ์ ์ง์  ํฌํจ์ํค์ง ์์
>>>- URI์ ๋ช์ฌ๋ฅผ ์ฌ์ฉํจ
>- ์ค์ ๋ฒ
>>- Jackson library
>>>- jackson-databind ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ ๊ฐ์ฒด๋ฅผ JSON ํฌ๋งท์ ๋ฌธ์์ด๋ก ๋ณํ์์ผ ๋ธ๋ผ์ฐ์ ๋ก ์ ์ก
>>>>- https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind
>>>- jackson-dataformat-xml ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ ๊ฐ์ฒด๋ฅผ xml๋ก ๋ธ๋ผ์ฐ์ ์ ์ ์ก
>>>>- https://mvnrepository.com/artifact/com.fasterxml.jackson.dataformat/jackson-dataformat=xml
>>>- pom.xml์ library ์ถ๊ฐ
>>>> ```xml
>>>> <!-- https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-core -->
>>>> <dependency>
>>>>     <groupId>com.fasterxml.jackson.core</groupId>
>>>>     <artifactId>jackson-core</artifactId>
>>>>     <version>${jackson-databind-version}</version>
>>>> </dependency>
>>>> ```
>- REST Annotation
>>- Annotation|Description
>>   :--|:--
>>   @RestController|Controller๊ฐ REST๋ฐฉ์์ ์ฒ๋ฆฌํ๊ธฐ ์ํ ๊ฒ์์ ๋ช์
>>   @ResponseBody|JSP ๊ฐ์ ๋ทฐ๋ก ์ ๋ฌ๋๋ ๊ฒ์ด ์๋๋ผ ๋ฐ์ดํฐ ์์ฒด๋ฅผ์ ๋ฌ
>>   @PathVariable|URL ๊ฒฝ๋ก์ ์๋ ๊ฐ์ ํ๋ผ๋ฏธํฐ๋ก ์ถ์ถ
>>   @CrossOrigin|Ajax์ ํฌ๋ก์ค ๋๋ฉ์ธ ๋ฌธ์ ๋ฅผ ํด๊ฒฐ
>>   @RequestBody|JSON ๋ฐ์ดํฐ๋ฅผ ์ํ๋ ํ์์ผ๋ก ๋ฐ์ธ๋ฉ
>- ์ค์  ์ฌ์ฉ ์์
>>- GET
>>> ```js
>>> // list.jsp
>>> $.ajax({
>>>   url:'${root}/admin/user',
>>>   type:'GET',
>>>   contentType:'application/json;charset=utf-8',
>>>   dataType:'json',
>>>   success:function(users) {
>>>     makeList(users);
>>>   },
>>>   error:function(xhr,status,msg) {
>>>     console.log("์ํ๊ฐ:"+status+" Http์๋ฌ๋ฉ์์ง:"+msg);
>>>   }
>>> });
>>> ```
>>> ```java
>>> // AdminController.java
>>> @RequestMapping(value="/user", method=RequestMethod.GET, headers={"Content-type=application/json"})
>>> public List<MemberDto> userList() {
>>>   return userService.userList();
>>> }
>>> ```
>>- POST
>>> ```js
>>> // list.jsp
>>> $("#registerBtn").click(function() {
>>>   let registerinfo=JSON.stringify({
>>>     "username":$("#username").val(),
>>>     "userid":$("#userid").val(),
>>>     "userpwd":$("#userpwd").val(),
>>>     "email":$("#email").val(),
>>>     "address":$("#address").val()
>>>   });
>>>   $.ajax({
>>>     url:'${root}/admin/user',
>>>     type:'POST',
>>>     contentType:'application/json;charset=utf-8',
>>>     dataType:'json',
>>>     success:function(users) {
>>>       $("#username").val('');
>>>       $("#userid").val('');
>>>       $("#userpwd").val('');
>>>       $("#email").val('');
>>>       $("#address").val('');
>>>       $("#userRegModal").modal('hide');
>>>       makeList(users);
>>>     },
>>>     error:function(xhr,status,msg) {
>>>       console.log("์ํ๊ฐ:"+status+" Http์๋ฌ๋ฉ์์ง:"+msg);
>>>     }
>>>   });
>>> });
>>> ```
>>> ```java
>>> // AdminController.java
>>> @RequestMapping(value="/user", method=RequestMethod.POST, headers={"Content-type=application/json"})
>>> public List<MemberDto> userRegister(@RequestBody MomberDto memberDto) {
>>>   userService.userRegister(memberDto);
>>>   return userService.userList();
>>> }
>>> ```
>>- PUT
>>> ```js
>>> // list.jsp
>>> $(document).on("click", ".modifyBtn", function() {
>>>   let mid=$(this).parents("tr").attr("data-id");
>>>   let modifyinfo=JSON.stringify({
>>>     "userid":mid,
>>>     "userpwd":$("#userpwd"+mid).val(),
>>>     "email":$("#email"+mid).val(),
>>>     "address":$("#address"+mid).val()
>>>   });
>>>   $.ajax({
>>>     url:'${root}/admin/user',
>>>     type:'PUT',
>>>     contentType:'application/json;charset=utf-8',
>>>     dataType:'json',
>>>     data:modifyinfo,
>>>     success:function(users) {
>>>       makeList(users);
>>>     }
>>>   });
>>> });
>>> ```
>>> ```java
>>> // AdminController.java
>>> @RequestMapping(value="/user", method=RequestMethod.PUT, headers={"Content-type=application/json"})
>>> public List<MemberDto> userModify(@RequestBody MomberDto memberDto) {
>>>   userService.userModify(memberDto);
>>>   return userService.userList();
>>> }
>>> ```
>>- DELETE
>>> ```js
>>> // list.jsp
>>> $(document).on("click", ".delBtn", function() {
>>>   if(confitm("์ญ์ ํ์๊ฒ ์ต๋๊น?")) {
>>>     let delid=$(this).parents("tr").attr("data-id");
>>>     $.ajax({
>>>       url:'${root}/admin/user'+delid,
>>>       type:'DELETE',
>>>       contentType:'application/json;charset=utf-8',
>>>       dataType:'json',
>>>       success:function(users) {
>>>         makeList(users);
>>>       }
>>>       error:function(xhr,status,msg) {
>>>         console.log("์ํ๊ฐ:"+status+" Http์๋ฌ๋ฉ์์ง: "+msg);
>>>       }
>>>     });
>>>   }
>>> });
>>> ```
>>> ```java
>>> // AdminController.java
>>> @RequestMapping(value="/user", method=RequestMethod.DELETE, headers={"Content-type=application/json"})
>>> public List<MemberDto> userDelete(@PathVariable("userid") String userid) {
>>>   userService.userDelete(userid);
>>>   return userService.userList();
>>> }
>>> ```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

## SpringBoot

>- ์ฅ์ 
>>- project์ ๋ฐ๋ผ ์์ฃผ ์ฌ์ฉ๋๋ library๋ค์ด ๋ฏธ๋ฆฌ ์กฐํฉ๋์ด ์์
>>- ๋ณต์กํ ์ค์ ์ ์๋์ผ๋ก ์ฒ๋ฆฌ
>>- ๋ด์ฅ ์๋ฒ๋ฅผ ํฌํจํด์ tomcat๊ณผ ๊ฐ์ WAS๋ฅผ ์ถ๊ฐ๋ก ์ค์นํ์ง ์์๋ ๊ฐ๋ฐ ๊ฐ๋ฅ
>>- WAS์ ๋ฐฐํฌํ์ง ์๊ณ ๋ ์คํํ  ์ ์๋ JARํ์ผ๋ก Web Application์ ๊ฐ๋ฐํ  ์ ์์
>- project ์์ฑ ๊ตฌ์กฐ ๋ฐ ์ฃผ์ ๊ตฌ์ฑ ํด๋/ํ์ผ
>>- ํ๋ก์ ํธ์ ์ฃผ์ ํ์ผ|์ค๋ช
>>   :--|:--
>>   src/main/java|java source directory
>>   HelloSpringBootApplication.java|application์ ์์ํ  ์ ์๋ main mathod ๊ฐ ์กด์ฌํ๋ ์คํ๋ง ๊ตฌ์ฑ ๋ฉ์ธ ํด๋์ค
>>   static|css,js,img ๋ฑ์ ์ ์  resource directory
>>   templates|SpringBoot์์ ์ฌ์ฉ๊ฐ๋ฅํ ์ฌ๋ฌ๊ฐ์ง View Template(Thymeleaf, Velocity,FreeMarker ๋ฑ) ์์น
>>   application.properties|application ๋ฐ ์คํ๋ง์ ์ค์  ๋ฑ์์ ์ฌ์ฉํ  ์ฌ๋ฌ๊ฐ์ง property๋ฅผ ์ ์ํ file
>>   src/main|jsp๋ฑ์ ๋ฆฌ์์ค directory
>- Swagger
>>- Swagger๋ฅผ ์ด์ฉํ REST API ๋ฌธ์ํ
>>>- ํ๋ก์ ํธ ๊ฐ๋ฐ์ ์ผ๋ฐ์ ์ผ๋ก ํ๋ก ํธ์๋์ ๋ฐฑ์๋ ๊ฐ๋ฐ์๊ฐ ๋ถ๋ฆฌ๋์ด ๊ฐ๋ฐํจ
>>>- ํ๋ก ํธ์๋ ๊ฐ๋ฐ์์ ๊ฒฝ์ฐ ํ๋ฉด๊ณผ ๋ก์ง์ ์ง์คํ๊ณ  ๋ฐฑ์๋ ๊ฐ๋ฐ์๊ฐ ๋ง๋  ๋ฌธ์ API๋ฅผ ๋ณด๋ฉฐ ๋ฐ์ดํฐ ์ฒ๋ฆฌ๋ฅผ ํจ
>>>- ๊ฐ๋ฐ ์ํฉ์ ๋ณํ์ ๋ฐ๋ผ API์ ์ถ๊ฐ ๋๋ ๋ณ๊ฒฝํ  ๋ ๋ง๋ค ๋ถํธํจ ๋ฐ์
>>>- ์ด ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด Swagger๋ฅผ ์ฌ์ฉ
>>- Swagger๋
>>>- ๊ฐ๋จํ ์ค์ ์ผ๋ก ํ๋ก์ ํธ์ API ๋ชฉ๋ก์ ์น์์ ํ์ธ ๋ฐ ํ์คํธํ  ์ ์๊ฒ ํด์ฃผ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ
>>>- Controller์ ์ ์๋์ด ์๋ ๋ชจ๋  URL์ ๋ฐ๋ก ํ์ธํ  ์ ์์
>>>- API ๋ชฉ๋ก๊ณผ API์ ๋ช์ธ ๋ฐ ์ค๋ช๋ ๋ณผ ์ ์์ผ๋ฉฐ API๋ฅผ ์ง์  ํ์คํธ๋ ๊ฐ๋ฅํจ