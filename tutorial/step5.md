# 6. 객체(Object)

## 6.1 객체란?
> 속성과 값을 담을 수 있는 구문으로 객체를 담을 수도있고, 함수를 담을 수도 있다.

- 값으로 활용할 때 가장 많이 쓰인다. (인덱스로만 움직이는 자료구조)
- 숫자, 문자열, boolean, 함수, 객체, 배열 등이 모두 배열을 구성 가능하다.
- 배열의 값을 순차적으로 넣는데 push() 를 권장한다.
- 배열에선 var arry = []; 리터럴 방식을 권장한다.
- 대괄호[]를 사용해 생성하고 안에 쉼표로 구분해 자료를 입력한다.


## 6.2 객체지향 프로그래밍 
> 가독성이 좋으며, 유지보수에 용이하다.
[하이브랩컨벤션](https://github.com/telltrue33/telltrue33.github.io/blob/master/convention/03_Prototype.md)


> for문을 돌려서 객체 가져오는 방법 

```
for( var key in obj) {
  console.log(key(속성을 가져오고),obj[key](값을 가져온다));
}
```

> 속성 삭제방법

```
delecte obj.tel;
```


### 기본구조
```html
<script src="http://code.jquery.com/jquery-latest.js"></script>
<script>
(function (win, $) { // win 자체가 객체이다
    'use strict'; // 자바스크립트 엄격모드 
    var objFunc = {
        init : function () {
            this.setElements();
            this.bindEvents();
        },
        setElements : function () {  // 성격에 맞는 것만 안에 선언해준다.
            this.btn = $('.btn');
        },
        bindEvents : function () {
            this.btn.on('click', $.proxy(this.viewFunc, this));
        },
        viewFunc : function (e) {
            $(e.currentTarget).parent().addClass('active');
        }
    };
    $(function () {
        objFunc.init();
    });
})(window, window.jQuery);
</script>
</body>
```

### 플러그인 제작
> $.fn.함수 (플러그인 선언)

> new로 호출하면 this로 쓸 수 있다(함수객체화)

```javascript
(function (win, $) 
  $.fn.customPlugin = funtion() { 
    for(var i = 0, max = this.length; i < max; i++){ 
      new studyPj.eq(i);
    }
  } 
  $(function(){ 
    Selector.customPlugin();
  }
 })(window, window.jQuery);
```


<br>

## 6.3 객체 내부 this 관리

- $.proxy(this.function, this)
- $(e.crruntTarget)
- arguments[0] : 인수 set 참조

``` 
this.변수;
this.변수;
this.변수;
this.변수;  // ';'로 쓰자. 객체 한줄에 저장 끝.
```
```
btn.on('click', function(){
  var _this = $(this);
}
```
저장하고 쓰는게 셀렉터를 또 읽지 않는 이유로 성능최적화에 더 좋다.



## 6.4 trim() 의 사용
> 문자를 비교하거나 했을 떄 실수로 들어가는 것들(공백) 제외하고 **문자만!** 가져올 수 있다.

````
var _this = $(e.currentTarget);
$.trim(_this.text());
```
