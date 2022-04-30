# **Vue.js** 🎥

### 참고자료

- 한 권으로 배우는 Vue.js 3

## 목차
>- [Vue.js 개요](#vuejs-개요)
>>- [Vue.js](#vuejs)
>>- [특징](#특징)
>>- [MVVM Pattern](#mvvm-pattern)
>>- [설치방법](#설치방법)
>>- [기초 프레임](#기초-프레임)
>- [Vue Instance](#vue-instance)
>>- [Vue Instance 생성](#vue-instance-생성)
>>- [Vue Instance Life-Cycle](#vue-instance-life-cycle)
>- [template - 보간법(interpolation)](#template---보간법interpolation)
>- [template - Directice](#template---directice)

<br>

---

## Vue.js 개요
>### Vue.js
>- 사용자 인터페이스를 만들기 위해 사용하는 오픈 소스 프레임워크
>- Options API와 컴포지션 API의 존재로 프로젝트 규모에 따라 적절한 방식을 선택할 수 있음
>>- Options API: 하나의 객체를 하나의 모듈로 만들어 컴포넌트라 칭하는 라이브러리
>>>- 소규모 혹은 중간급 규모의 웹 애플리케이션을 제작하는데 가장 손쉬운 선택
>>>- 하나의 객체를 변수와 메서드 등과 같은 특정합 옵션 기능으로 나눔
>>>- 하나의 변수와 연관된 수많은 기능들이 하나의 SFC(Single File Component) 의 이곳 저곳에 산포되어 가독성을 떨어뜨리고 코드 유지비용을 증가시킴
>>- 컴포지션 API
>>>- 컴포넌트를 작성할 때 함수 기반의 방법으로 작성
>>>- 특정 역할에 따른 함수의 분리 등을 통하여 훨씬 가독성 높고 잘 조직화된 코드를 만듬
>>>- 컴포지션 API를 통해 은닉화된 코드는 컴포넌트들이 재활용할 수 있음

<br>

[목차로 이동](#목차)

>### 특징
>- 접근성
>- 유연성
>- 고성능

<br>

[목차로 이동](#목차)

>### MVVM Pattern
>- Model + View + ViewModel
>>- Model: 순수 자바스크립트 객체
>>- View: 웹 페이지의 DOM
>>- ViewModel: Vue
>>>- 기존에는 자바스크립트로 View에 해당하는 DOM에 접근하거나 수정하기 위해 jQuery와 같은 라이브러리를 이용
>>>- Vue는 View와 Model을 연결하고 자동으로 바인딩하여 양방향 통신을 가능케 함

<br>

[목차로 이동](#목차)

>### 설치방법
>- Direct \<script> include
>>- download
>>- CDN: \<script src="https://cdn,jsdelivr.net/npm/vue/dist/vue.js">\</script>
>- NPM
>- CLI
>- [가이드 링크](https://vuejs.org/guide/quick-start.html)

<br>

[목차로 이동](#목차)

>### 기초 프레임
>- ```html
>   <!DOCTYPE html>
>   <html lang="en">
>   <head>
>     <meta sharset="UTF-8">
>     <meta name="viewport" content="width=device-width, inital-scale=1.0">
>     <title>Vue.js</title>
>     <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
>   </head>
>   <body>
>     <div id="app">
>       <h2>{{message}}</h2>
>     </div>
>     <script>
>       new Vue({
>         el:'#app',
>         data: {
>           message: '첫 번쨰 Vue.js 앱'
>         }
>       });
>     </script>
>   </body>
>   </html> 
>   ```

<br>

[목차로 이동](#목차)

---

## Vue Instance
>### Vue Instance 생성
>- Vue Instance 생성 코드
>>```html
>><script>
>>  new Vue({ // 인스턴스
>>    el:'#app',
>>    data: {
>>      message: '첫 번쨰 Vue.js 앱'
>>    }
>>  });
>></script>
>>```
>>> 속성|설명
>>> :--|:--
>>> el|Vue가 적용될 요소 지정. CSS Selector or HTML Element
>>> data|Vue에서 사용되는 정보 저장. 객체 또는 함수의 형태
>>> template|화면에 표시할 HTML, CSS 등의 마크업 요소를 정의하는 속성. 뷰의 데이터 및 기타 속성들도 함께 화면에 그릴 수 있음
>>> methods|화면 로직 제어와 관계된 method를 정의하는 속성. 마우스 클릭 이벤트 처리와 같이 화면의 전반적인 이벤트와 화면 동작과 관련된 로직을 추가
>>> created|Vue Instance가 생성되자 마자 실행할 로직을 정의
>- Vue Instance의 유효범위
>>- Vue Instance를 생성하면 HTML의 특정 범위 안에서만 옵션 속성들이 적용
>>- el 속성과 밀접한 관련이 있음
>>- 인스턴스가 화면에 적용되는 과정
>>>1. 뷰 라이브러리 파일 로딩
>>>2. Vue()로 인스턴스 객체 생성(옵션 속성 포함)
>>>3. el 속성에 지정한 특정 화면 요소(DOM)에 인스턴스를 붙임
>>>4. data 속성이 el 속성에 지정한 화면 요소와 그 이하 레벨의 화면 요소에 적용되어 값이 치환
>>>5. 변환된 화면 요소를 사용자가 최종 확인

<br>

[목차로 이동](#목차)

---

## Vue Instance Life-Cycle
>- Life Cycle은 Instance의 생성, 생성된 Instance를 화면에 부착, 화면에 부착된 Instance의 내용이 갱신, Instance가 제거되는 소멸의 4단계로 나뉨
>- Life Cycle 속성|설명
>   :--|:--
>   beforeCreate|Vue Instance가 생성되고 각 정보의 설정 전에 호출, DOM과 같은 화면요소에 접근 불가
>   created|Vue Instance가 생성된 후 데이터들의 설정이 완료된 후 호출. Instance가 화면에 부착하기 전이기 때문에 template 속성에 정의된 DOM 요소는 접근 불가. 서버에 데이터를 요청(http 통신)하여 받아오는 로직을 수행하기 좋음
>   beforeMount|마운트가 시작되기 전에 호출
>   mounted|지정된 element에 Vue Instance 데이터가 마운트 된 후에 호출. template 속성에 정의한 화면 요소에 접근할 수 있어 화면 요소를 제어하는 로직 수행
>   beforeUpdate|데이터가 변경될 때 virtual DOM이 랜더링, 패치 되기 전에 호출
>   updated|Vue에서 관리되는 데이터가 변경되어 DOM이 업데이트 된 상태. 데이터 변경 후 화면 요소 제어와 관련된 로직을 추가
>   beforeDestroy|Vue Instance가 제거되기 전에 호출
>   destroyed|Vue Instance가 제거된 후에 호출

<br>

[목차로 이동](#목차)

---

## template - 보간법(interpolation)
>### 보간법(interpolation)
>- 문자열
>>- 데이터 바인딩의 가장 기본 형태는 "Mustache" 구분(이중 중괄호)을 사용한 텍스트 보간
>>>- {{ 속성명 }}
>>- v-once 디렉티브를 사용하여 데이터 변경 시 업데이트 되지 않는 일회성 보간을 수행
>>>```html
>>><span>메시지: {{msg}}</span>
>>><span v-once>변경되지 않음</span>
>>>```
>- 원시 HTML
>>- 이중 중괄호는 HTML이 아닌 일반 텍스트로 데이터를 해석함
>>- 실제 HTML을 출력하려면 v-html 디렉티브 사용
>>>```html
>>><div id="app">
>>>  <div>메세지: {{message}}</div>
>>>  <div v-text="'메세지: '+message">무시</div>
>>>  <div v-html="'메세지: '+message">무시</div>
>>></div>
>>><script>
>>>  new Vue({
>>>    el: '#app',
>>>    data: {
>>>      message: '<h2>Hello</h2>'
>>>    }
>>>  });
>>></script>
>>>```
>- JavaScript 표현식 사용
>>- Vue.js는 모든 데이터 바인딩 내에서 JavaScript 표현식의 모든 기능을 지원함
>>>```html
>>>{{number+1}}
>>>{{ok?'YES':'NO'}}
>>>{{message.split('').reverse().join('')}}
>>><div v-bind:id="'list-'+id"></div>
>>>```
>>- 한 가지 제한사항으로 각 바인딩에 하나의 단일 표현식만 포함될 수 있음
>>>```html
>>>{{var a=1}} <!-- 구문은 표현식이 아님 -->
>>>{{if(ok) {return message}}} <!-- 조건문은 작동하지 않으므로 삼항 연산자를 이용 -->
>>>```

<br>

[목차로 이동](#목차)

---

## template - Directice
>### 디렉티브(Directives)
>- 특징
>>- 디렉티브는 v-접두사가 있는 특수 속성
>>- 디렉티브 속성 값은 단일 JavaScript 표현식이 됨 (v-for 예외)
>>- 디렉티브의 역할은 표현식의 값이 변경될 때 사이드 이펙트를 반응적으로 DOM에 적용
>- 구성요소
>> v-text|v-bind|v-else|v-html
>>  :--|:--|:--|:--
>>  v-show|v-for|v-once|v-if
>>  v-cloak|v-model|v-else-if|v-on
>>- v-model
>>>- 양방향 바인딩 처리 (from의 input, textarea에 사용)
>>>- ```html
>>>   <input type="text" v-model="msg">
>>>   ```
>>- v-bind
>>>- 엘리먼트 속성과 바인딩 처리를 위해 사용
>>>- ':' 약어로 사용 가능
>>>- ```html
>>>   <div v-bind:id="idValue">v-bind</div>
>>>   <div :id="idValue">v-bind</div>
>>>   <button v-bind:[key]="btnId">버튼</button>
>>>   <button :[key]="btnId">버튼</button>
>>>   <a v-bind:href="link1">다음</a>
>>>   <a :href="link2">네이버</a>
>>>   ```
>>- v-show
>>>- 조건에 따라 엘리먼트를 화면에 랜더링
>>>- style의 display를 변경
>>>- ```html
>>>   <div v-show="isShow">{{msg}}</div>
>>>   ```
>>- v-if, v-else-if, v-else
>>>- 조건에 따라 엘리먼트를 화면에 랜더링
>>>- ```html
>>>   <input type="number" v-model="age" />
>>>   <span v-if="age < 10">무료</span>
>>>   <span v-else-if="age < 13">1000원</span>
>>>   <span v-else-if="age < 60">3000원</span>
>>>   <span v-else>5000원</span>
>>>   ```
>>- v-show 와 v-if의 차이점
>>> &nbsp|v-if|v-show
>>>  :--|:--|:--
>>>  랜더링|false인 경우 x|항상 o
>>>  false 인 경우|엘리먼트 삭제|display:none 적용
>>>  template 지원|o|x
>>>  v-else 지원|o|x
>>- v-for
>>>- 배열이나 객체의 반복에 사용
>>>- v-for="요소변수이름 in 배열" 또는 v-for="요소변수이름,인덱스) in 배열
>>>- ```html
>>>   <ul>
>>>     <li v-for="name in regions">{{name}}</li>
>>>   </ul>
>>>   ```
>>- template
>>>- 여러 태그들을 묶어서 처리해야 할 경우 사용
>>>- 주로 v-if, v-for, component 등과 함께 사용
>>>- ```html
>>>   <template v-if="count%2 == 0">
>>>     <h4>각 태그에 v-if 할 필요없이 한번에 처리</h4>
>>>     <h4>각 태그에 v-if 할 필요없이 한번에 처리</h4>
>>>     <h4>각 태그에 v-if 할 필요없이 한번에 처리</h4>
>>>   </template>
>>>   <template v-for="(region, index) in school" v-if="region.count == count">
>>>     <h1>지역:{{region.name}} ({{region.count}}학급)</h1>
>>>   </template>
>>>   ```
>>- v-cloak
>>>- Vue Instance가 준비될 때까지 mustache 바인딩을 숨기는데 사용
>>>- [v-cload] {display:none} 같은 CSS 규칙과 함께 사용
>>>- Vue Instance가 준비되면 v-cloak는 제거됨
>>>- ```html
>>>   <style>
>>>     [v-cloak]::before {
>>>       content: '로딩중';
>>>     }
>>>     [v-cloak] > * {
>>>       display: none;
>>>     }
>>>   </style>
>>>   <div id="app">
>>>     <h3>1. 일반 - {{msg}}</h3>
>>>     <div v-cloak>
>>>       <h3>2. v-cloak - {{msg}}</h3>
>>>     </div>
>>>   </div>
>>>   <script>
>>>     setTimeout(function(){
>>>       new Vue({
>>>         el: "#app",
>>>         data: {
>>>           msg: "hello"
>>>         }
>>>       });
>>>     }, 3000);
>>>   </script>
>>>   ```
>>- Vue method
>>>- Vue Instance는 생성과 관련된 data 및 method의 정의 가능
>>>- method 안에서 data를 "this.데이터이름" 으로 접근 가능
>>>- ```html
>>>   <div id="app">
>>>     <div>data: {{message}}</div>
>>>     <div>method kor: {{helloKor()}}</div>
>>>     <div>method eng: {{helloEng()}}</div>
>>>   </div>
>>>   <script>
>>>     new Vue({
>>>       el: "#app",
>>>       data: {
>>>         message: "hello", name: "홍길동"
>>>       },
>>>       methods: {
>>>         helloEng() {
>>>           return "hello "+this.name
>>>         },
>>>         helloKor() {
>>>           return "안녕 "+this.name
>>>         }
>>>       }
>>>     });
>>>   </script>
>>>   ```

<br>

[목차로 이동](#목차)

---

