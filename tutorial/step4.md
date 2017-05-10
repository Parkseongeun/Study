# 5. 배열

> 하나의 변수에 여러 개의 데이터를 담을 수 있는 그릇



- 값으로 활용할 때 가장 많이 쓰인다. (인덱스로만 움직이는 자료구조)
- 숫자, 문자열, boolean, 함수, 객체, 배열 등이 모두 배열을 구성 가능하다.
- 배열의 값을 순차적으로 넣는데 push() 를 권장한다.
- 배열에선 var arry = []; 리터럴 방식을 권장한다.
- 대괄호[]를 사용해 생성하고 안에 쉼표로 구분해 자료를 입력한다.

```javascript
var tagPush = ''; // String으로 쓰겠다.
var arrayObj = []; // 리터럴 방식 
arrayObj.push(데이터1); 
arrayObj.push(데이터2); 
arrayObj.push(데이터3);
```

```html
<script>
// 배열 생성 및 요소 추가
var array = [];
array[0] = 데이터 1;
array[1] = 데이터 2;
array[2] = 데이터 3;

// 배열 요소에 접근하는 방법
var array2 = [273, 'String', true, function () {}, {}, [273, 103]];
console.log(array2[3]);

// 배열 길이 체크
var array3 = [10, 20];
console.log(array3.length);
// 다시 초기화
array3 = [];
console.log(array3.length);
</script>
```

<br><br>
## 5.1 배열이 가지고 있는 메소드


- join : 문자열로 리턴
- reverse : 거꾸로 변경
- sort : 배열 정렬
- concat : 배열 이어붙임
- slice : 부분배열변환
- splice : 삭제/추가
- push, pop : 맨뒤 추가/삭제
- shift, unshift : 맨앞 추가/삭제