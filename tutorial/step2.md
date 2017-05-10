# 2. 코드 작성법
<br><br>
## 2.1 변수 선언 (var)
> 변동하는 값을 찾아 변수로 치환한다. 

```
var a; // 이 변수에는 어떠한 값을 넣어도 가능하다.  
a = 10; // number 
a = 홍길동; // String 
a = true;  // boolean 
a = new Object();  // Object 
a = function(){};  // function
```

<br><br>
## 2.2 index 의 활용
> 배열 형태의 요소의 순서값(0부터 시작)<br>.eq(index number)를 활용하여 손쉽게 접근 가능하다.<br>[예제1](https://parkseongeun.github.io/Study/exam2/if.html)<br>[예제2](https://parkseongeun.github.io/Study/exam3/if.html)

<br><br>
## 2.3 jQuery API 활용
> [https://oscarotero.com/jquery/](https://oscarotero.com/jquery/)


**많이 쓰이는 메소드 정리**
> [Effects](https://github.com/Parkseongeun/Study/blob/gh-pages/exam3/jquery_reference.md)

<br><br>
## 2.4 console.log
> 변수 및 다양한 정보들을 확인할 수 있는 함수이다.<br>개발소스에 영향을 주지 않고 주로 디버깅(버그수정) 용도로 사용한다.<br>IE하위(8이하)버전에서는 지원하지 않는다.

```
var a = 2;
var b = 3; 
console.log(a*b);
```
console창에는 **6** 이 출력된다.

<br><br>
## 2.5 Comment(주석)
> 개발소스의 코드를 설명하거나 기타 참조사항을 기록하기 위해 사용한다. (개발소스에 영향을 주지 않는다) <br>좋은 코드는 좋은 주석을 가지고 있는 코드이다. (유지보수, 개발자간의 소통 용이)

```
// 한줄 주석

/*
  여러줄
  주석
*/
```
