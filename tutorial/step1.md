# 1. 자바스크립트 소개
<br><br>
## 1.1 javascript vs jQuery
> jQuery는 **크로스브라우징**을 지원하는 점에서 javascript와 제일 큰 차이점이 있으며, 1차적으로는 모든 태그에 손쉽게 접근(Selector) 할 수 있다는 장점이 있다.

```md
document.getElementById(); // javascript 문법에서의 id로 태그 접근
document.getElementsByClassName(); // javascript 문법에서의 class로 태그 접근
```
```md
$('#idName').메소드(); // jquery 문법에서의 id로 태그 접근
$('.classNmae').메소드(); // jquery 문법에서의 class로 태그 접근
```



**ie8 이하 크로스브라우징 이슈**

- [http://caniuse.com](http://caniuse.com) 에서 체크 가능
- javascript vs jQuery 셀렉터 체크
  1. [selector_jQuery](https://parkseongeun.github.io/Study/exam1/selector_jQuery.html)
  2. [selector_javascript](https://parkseongeun.github.io/Study/exam1/selector_javascript.html)
  3. [selector2_jQuery](https://parkseongeun.github.io/Study/exam1/selector2_jQuery.html)
  4. [selector2_javascript](https://parkseongeun.github.io/Study/exam1/selector2_javascript.html)

```
- getElementsByClassName (querySelectorAll로는 태그 접근이 가능하다)
- childNodes()
- previousSibling()
- nextSibling()
```


**get(0)**

> jQuery 선택자에 get(0)을 붙이면 javascript선택자로 바꿀 수 있다(속도가 더 빠름)

```
html('값') -> .get(0).innerHTML = 값;
```

<br><br>
## 1.2 함수 선언 방법



**선언함수 선언 방식**

> 함수 선언 전, 후에 함수 호출이 가능(함수 호이스팅)한 방식

```javascript
function 함수명() {
  함수내용
}
함수명();
```


**익명함수 선언 방식**

> 함수를 호출하는 데에 있어 혼란주지 않기 위해 함수 밑에 호출하는 방식, 함수 호이스팅 방지의 이유로 권장한다.

```javascript
var 함수명 = function () {
   함수내용
}; 
함수명(); // 함수 선언보다 위에서 호출할 경우 실행안됨(에러발생)
```
<br><br>

## 1.3 즉시실행함수
> 다른 코드와 충돌방지를 위해 쓰인다. <br>반응형 브라우저 체크, 디바이스 체크, load된 후 한번만 쓰고 버릴 함수에 보통 쓰인다.

```javascript
<script>
(function() {

})(win,&); // (window, window.jQuery)의 약자로 고유명사라서 충돌나지 않기때문에 쓴다.
</script>
```
<br><br>

## 1.4 인자(파라미터)
> 함수로 유입되는 입력값


```javascript
function sum(a,b) {
  var c = a + b;
  return c; // 반환값
  return { // 객체를 반환할 수도 있다 (권장하지 않음)
    init : function() {

    }
  }
}
var idx = sum(2,5); // 변수 idx는 **7**값을 가지게 된다.
```
```
(function() {

})(인자값, 인자값);
```
<br><br>

## 1.5 도큐먼트 오브제트 모델 (DOM)
```javascript
$(document).ready(function(){
 // DOM태그들을 다 읽고난 후(ready) 스크립트를 실행하겠다.
 // 떄문에 스크립트를 읽기를 기다리는 동안 style이 안불러와져서 화면이 깨져보이는 불상사를 막을 수 있다.
 // javascript 에서도 allNode라는 것이 있지만 느리다.
 // window.onload 는 DOM 및 모든 리소스를 불러온 후에 실행한다.
})
```
```javascript
$(function(){  // 권장약어
 ~~
})
```

<br><br>
## 1.6 .on() vs .bind()
> .on() : DOM이 동적으로 생성될 경우 계속 탐색 후 실행한다.<br>.bind() : 새로 생성된 DOM은 처리 불가능하다.

<br><br>
## 1.7 jQuery의 활용
> 비슷한 형태, 성격끼리 묶어 놓는다. (유지보수에 용이하다)

```
선택자
함수
선택자
함수
```
보다 아래를 권장

```
선택자
선택자
함수
함수
```
