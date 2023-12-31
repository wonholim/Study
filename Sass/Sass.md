# Sass

- [x] Sass란?
- [x] 설치 및 설정
- [x] 기본 문법
  - [x] 변수
  - [x] 중첩
  - [x] partials and import
  - [x] 믹스인과 인클루드
  - [x] 연산자 사용
- [x] 고급 문법
  - [x] 함수
  - [x] 조건문과 반복문
  - [x] 플레이스홀더와 확장
- [x] 참고 자료

---

<br/><br/>

## Sass란?

---

<br/>

- CSS는 웹페이지의 스타일을 지정하는 도구이지만, 실제로 프로젝트에 작업을 할 때, 제약 사항과 한계가 존재한다.
  - CSS에는 변수를 사용할 수 없어, 동일한 값이 여러 곳에서 반복되는 경우 유지 보수가 어렵다.
  - CSS로 중복 코드를 효과적으로 관리하기 어렵다.
  - 코드의 양이 많이 질 때, CSS 코드는 길고 복잡해질 수 있다.
  - CSS는 조건문, 반복문 등의 로직을 사용할 수 없다.

<br/><br/>

- Sass는 CSS의 문제를 해결하기 위해 등장한 CSS 전처리기이다. (CSS가 만들어지기 전에 먼저 처리해 준다.)
  - Sass는 변수를 사용할 수 있다.
  - Sass는 믹스인, 함수 등의 기능을 통해, 코드의 재사용성을 높일 수 있다.
  - Saas는 모듈화, 중첩을 통해 코드를 구조화시킬 수 있다.
  - Sass 조건문, 반복문 기능을 제공한다.
  - Sass는 표준 CSS와 완벽하게 호환이되므로, 기존 CSS 코드를 그대로 사용하면서 Sass 기능을 도입할 수 있다.

<br/>

## 설치 및 설정

---

<br/>

- VSCode 기준

  <img width="772" alt="image" src="https://user-images.githubusercontent.com/56383948/260661995-d6c64d82-2cb8-4b45-9533-fd5a68620014.png">

  - Sass를 실시간으로 컴파일 해주는 플러그인

  <img width="772" alt="image" src="https://user-images.githubusercontent.com/56383948/260663375-e2140e0c-163b-40da-9b80-f9e185cad268.png">

  - Scss, CSS에만 초점을 맞춘 prettier

  <img width="772" alt="image" src="https://user-images.githubusercontent.com/56383948/260663592-8021f18e-8127-4f05-8665-862f5ab8ddcb.png">
  
  - scss파일을 저장할 때마다, 오류를 발견하면, 밑줄 및 강조표시를 하여 오률를 표시한다.

  <img width="772" alt="image" src="https://user-images.githubusercontent.com/56383948/260663708-57ffa9c9-12de-451f-a27b-b4a4a5219b9f.png">

  - scss 스니펫

  <img width="772" alt="image" src="https://user-images.githubusercontent.com/56383948/260663830-a062f7f9-ef0a-4179-89e8-749ce0fe5c70.png">

  - 자신이 속한 규칙의 이름과 함께 SCSS 코드의 닫는 괄호 옆, 주석을 추가해준다.

- 설치를 하고 난 뒤, .scss 또는 .sass파일을 생성하고, 하단의 live 버튼을 누르게 되면, 수정이 될 때 마다, 변경사항에 맞추어서 저장이된다.
  <img width="158" alt="image" src="https://user-images.githubusercontent.com/56383948/260666724-6b3ddcca-23bf-4d79-8a35-3ae6d4c7ceb1.png">

---

- 위 내용이 번거롭다면, scss파일을 저장하면 바로 css로 컴파일 해주는 익스텐션이 존재하고 또한 타입스크립트도 지원한다.
  <img width="733" alt="image" src="https://user-images.githubusercontent.com/56383948/260668733-1c48c20e-4ffb-4263-acd2-810f9becfd32.png">

<br/>

## 기본 문법

---

<br/>

- Sass에 대해 처음 접하면서 알게된 것은 Scss이다.
- Scss는 Sass의 버전 3에서 등장한 언어이다.
- Sass는 파이썬과 같이 들여 쓰기 + 줄 바꿈 형식을 지원한다.
- Scss는 기존 전통 언어와 같이 중괄호 + 세미콜론의 형식을 지원한다.
- Scss 문법을 기반으로 코드를 작성하게 되면, Sass의 전처리기 도움을 받고 컴파일러가 CSS로 빌드한다.
- `가장 중요한 점은, Sass보다 Scss를 선호하며, 대다수의 라이브러리, 프레임워크가 Scss 문법을 활용한다.`
- `.sass`와 `.scss`는 엄연히 다른 파일이다. 파일에 따라, 올바른 문법을 사용해야 한다.

<br/>

### 변수

<br/>

- Sass는 `Numbers`, `Strings`, `Colors`, `Booleans`, `Nulls`, `List`, `Maps`의 데이터 종류를 가지고 있다.

- 변수를 사용할 때는 `$`문자를 사용해서 변수를 선언하고 사용한다.

<img width="363" alt="image" src="https://user-images.githubusercontent.com/56383948/260671197-1d83d51d-f1b8-4c67-a849-1acb7467ef96.png">

> Scss의 경우

<img width="363" alt="image" src="https://user-images.githubusercontent.com/56383948/260671768-7a41ccd7-d810-486f-b905-d841c8ab7df6.png">

> Css로 빌드된 경우

![image](https://user-images.githubusercontent.com/56383948/260672453-d324948f-1bd1-4c94-85e3-508902755fd1.png)



<br/>

### 중첩

<br/>

- 일반적인 CSS에서는 특정 선택자 자식, 자손의 선택자를 스타링일 하려면 따로 선언을 해주야하는 불편함이 있었다.
- Sass에서는 {}안에 중첩해서, 적용이 가능하다.

```scss
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;

    li {
      display: inline-block;

      a {
        display: block;
        padding: 6px 12px;
        text-decoration: none;
      }
    }
  }
}

은 다음과 같이 변한다.

nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
nav ul li {
  display: inline-block;
}
nav ul li a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}
```

- & 기호를 사용해서 부모 선택자를 참조할 수 있다.

```scss
button {
  padding: 10px;
  background: blue;
  color: white;

  &:hover {
    background: darkblue;
  }

  &.disabled {
    background: gray;
    cursor: not-allowed;
  }
}

은 다음과 같이 변한다.

button {
  padding: 10px;
  background: blue;
  color: white;
}
button:hover {
  background: darkblue;
}
button.disabled {
  background: gray;
  cursor: not-allowed;
}
```

![image](https://user-images.githubusercontent.com/56383948/260674166-41b52fc1-ba2b-481f-9d2b-064aad36ae09.png)


<br/>

### partials and import

<br/>

- partials and import를 사용하면, 스타일 시트를 여러 파일로 분리하고, 재사용이 가능하다. 코드를 구조화시킬 수 있으며, 유지 보수를 돕는다.

- Partials의 경우 파일 이르이 _로 시작하는 scss파일은 partial로 간주한다.
- @import를 통해, partial파일을 다른 scss 파일에서 가져올 수 있다.

```scss
_var.scss
$primary-color: #3498db;
$secondary-color: #f39c12;

main.scss
@import 'var'; // 파일 확장자와 언더스코어를 생략할 수 있다.

body {
  background-color: $primary-color;
}

button {
  color: $secondary-color;
}

빌드 후

body {
  background-color: #3498db;
}

button {
  color: #f39c12;
}
```

<br/>

### 믹스인과 인클루드

<br/>

- Scss에서 Mixin은 재사용 가능한 스타일 블록을 정의하는 방법이고, @include 지시어를 사용해서, 해당 Mixin을 포함할 수 있다.

```scss
@mixin button-styles($bg-color, $text-color) {
  background-color: $bg-color;
  color: $text-color;
  padding: 10px 20px;
  border: none;
  text-align: center;
}

.primary-button {
  @include button-styles(#3498db, #fff);
}

.secondary-button {
  @include button-styles(#f39c12, #333);
}


css 파일 생성

.primary-button {
  background-color: #3498db;
  color: #fff;
  padding: 10px 20px;
  border: none;
  text-align: center;
}

.secondary-button {
  background-color: #f39c12;
  color: #333;
  padding: 10px 20px;
  border: none;
  text-align: center;
}
```

<br/>

### 연산자 사용

<br/>

- Scss에서는 수치 값에 대해 간단한 연산이 적용가능하다. 덧셈, 뺄셈, 곱셈, 나눗셈 등의 기본 연산자를 사용할 수 있다.

```scss
$padding: 10px;
$border-width: 2px;

.container {
  width: 300px - $border-width * 2;
  padding: $padding;
  border: $border-width solid #000;
}

빋드 후

.container {
  width: 296px;
  padding: 10px;
  border: 2px solid #000;
}
```

<br/>

## 고급 문법

---

<br/>


### 함수

<br/>

- Scss에서는 @function을 사용해서, 함수를 생성할 수 있다.

```scss
@function double($value) {
  @return $value * 2;
}

.container {
  width: double(150px);
}

빌드 후

.container {
  width: 300px;
}
```

- CSS에서 하나의 기능을 여러 컴포넌트에 적용을 시켜야 할 때, 함수를 사용하거나, 조건문을 같이 사용할 수 있다.

<br/>

### 조건문과 반복문

<br/>

- Scss에서는 @if, @else, @for 등의 지시어를 사용해서, 조건문과 반복문을 작성할 수 있다.

```scss
$theme: dark;

.button {
  @if $theme == dark {
    background-color: #000;
    color: #fff;
  } @else {
    background-color: #fff;
    color: #000;
  }
}

@for $i from 1 through 3 {
  .col-#{$i} {
    width: $i * 33.333%;
  }
}

빌드 후

.button {
  background-color: #000;
  color: #fff;
}

.col-1 {
  width: 33.333%;
}

.col-2 {
  width: 66.666%;
}

.col-3 {
  width: 99.999%;
}
```

<br/>

### 플레이스홀더와 확장

<br/>

- 플레이스홀더 선택자는 %문자와 함께 사용한다.
- 단독으로 사용할 경우 css에 컴파일이 되지 않는다.
- 함수나 변수를 사용하듯 내가 원하는 요소에 불러와서 사용할 수 있다.
- 만들어 놓은 플레이스홀더 선택자는 @extend를 통해 호출한다.

```scss
%button-shared {
  display: inline-block;
  padding: 10px 20px;
  border: none;
  text-align: center;
}

.primary-button {
  @extend %button-shared;
  background-color: #3498db;
}

.secondary-button {
  @extend %button-shared;
  background-color: #f39c12;
}

빌드 후

.secondary-button, .primary-button {
  display: inline-block;
  padding: 10px 20px;
  border: none;
  text-align: center;
}

.primary-button {
  background-color: #3498db;
}

.secondary-button {
  background-color: #f39c12;
}

단독으로 사용할 경우 css에 컴파일이 되지 않는다.

%button-unused {
  display: inline-block;
  padding: 10px 20px;
  border: none;
  text-align: center;
}

코드의 경우 빌드를 하면,

아무것도 존재하지 않는다.
```

<br/>

## 참고 자료

---

<br/>

> [인파](https://inpa.tistory.com/entry/SCSS-%F0%9F%92%8E-%EC%A1%B0%EA%B1%B4%EB%AC%B8-%EB%B0%98%EB%B3%B5%EB%AC%B8?category=890793), [sass](https://sass-lang.com/), [extend](https://www.w3schools.com/sass/sass_extend.php), [sass문법정리](https://seokzin.tistory.com/entry/SCSS-SCSS-%EB%AC%B8%EB%B2%95-%EC%A0%95%EB%A6%AC), [sass와 scss](https://nykim.work/97), [플레이스홀더](https://abcdqbbq.tistory.com/85)

<br/>
