# 3. 조건문
<br><br>
## 3.1 if문
> if 문은 단독으로도 사용가능하고 else 또는 else if 조건 분기문을 추가로 사용 가능하다.<br>값을 비교할 때 '==' 보다는 '==='(타입까지 동일한지 비교)를 권장한다.

```javascript
if (조건1) {
 // 조건1이 참이면 실행
} else if (조건2) {
 // 조건2이 참이면 실행
} else {
 // 조건1, 2에 해당하지 않을 때 실행
}
```
[예제보기](https://parkseongeun.github.io/Study/exam3/if.html)
<br><br>
## 3.2 switch문
> 값이 정해진 조건에 쓰기에 적합하다.

```javascript
var num = 50; 
 switch (num) { 
 case 15 : console.log('10'); 
 break; 
 case 50 : console.log('50'); 
 break; 
 default : // 값이 없을 경우 
 console.log('default'); 
 break; 
}
```
<br><br>
# 4. 반복문
<br><br>
## 4.1 while문
> 몇 번 돌아야할 지 모호할 때 흔히 사용하며, 특정 값을 구할때 사용하면 유용하다.

```javascript
var num = 0; 
while(num < 20){ // 조건문 
 console.log(num); 
 num++; // 증감연산자
}
```
<br><br>
## 4.2 for문
> for (변수선언; 조건문; 증감연산자)

```javascript
for (var num = 0; num < $('li').length; num++ ) {
 console.log(num); 
}
```
이렇게 하면 성능이슈면에서 li의 태그를 계속 읽고 length값을 계속 계산해줘야하기때문에

```javascript
for (var num = 0, max = $('li').length; num < max; num++ ) { 
 console.log(num); 
}
```
위 처럼 **max** 라는 특정 변수를 생성해 변수선언 부분에 미리 넣어주는 것이 좋다.


[예제보기](https://parkseongeun.github.io/Study/exam4/for_while.html)