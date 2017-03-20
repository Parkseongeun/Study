# Effects

## jQuery api 참고
[https://oscarotero.com/jquery/](https://oscarotero.com/jquery/)

## Basics
### .hide()
> 애니메이션 없이 요소를 감추고 싶을 때 쓰인다.
```md
$( "#ref_hide" ).hide();
```
```md
$( "#ref_show" ).show();
```
### .show()
> 애니메이션 없이 요소를 보이고 싶을 때 쓰인다.
```md
$( "#ref_show" ).show();
```
### .toggle()
> 요소를 보여줬다 감춰다를 반복할 때 쓰인다.
```md
$( "#ref_toggle" ).toggle();
```
```md
if ( display === true ) {
  $( "#ref_toggle" ).show();
} else if ( display === false ) {
  $( "#ref_toggle" ).hide();
}
```

## Custom
### .animate()
요소의 움직임, 속도제어 등 효과를 줄 수 있다.
duration, easing, queue , specialEasing, step, progress, complete, start, done, fail, always
```md
$( "#ref_animate" ).animate( properties [, duration ] [, easing ] [, complete ] )
```
```md
$( "#ref_animate" ).animate({
    opacity: 0.25,
    left: "+=50",
    height: "toggle"
  }, 5000);
```
### .clearQueue()
실행되지 않은 함수이 다 제거된다. `stop()`과 비슷한 맥락.
```md
$( "#ref_clearQueue").click(function() {
  var myDiv = $( "div" );
  myDiv.clearQueue();
  myDiv.stop();
});
```
### .delay()
요소에 어떠한 기능을 넣어줄 때 잠시 기다렸다가 줄 수 있다. (먼저 보였다가 잠시 후 사라지는 팝업에서 많이 쓰임)
```md
$( "#ref_delay").click(function() {
	$( "div" ).fadeIn( 300 ).delay( 800 ).fadeOut( 400 ); // delay 0.8초 후 fadeOut
});
```
### .dequeue()
dequeue 함수 호출 시 큐에서 빠져나와 다음 함수 실행이 된다.
```md
$( "#ref_dequeue").click(function() {
   $( "div" )
	.animate({ left:"+=200px" }, 2000 )
	.animate({ top:"0px" }, 600 )
	.queue(function() {
	$( this ).toggleClass( "red" ).dequeue();
   })
    .animate({ left:"10px", top:"30px" }, 700 );
});
```
### .finish()
요소에 해당하는 애니메이션 효과를 종료시킬 수 있다. 
(stop() 은 그 즉시 종료시키는 반면 애니메이션 결과의 마지막을 적용한 후 종료)
```md
$( "#ref_finish").finish();
```
### .jQuery.fx.Interval()
에니메이션 실행되는 초당 프레임의 개수를 조정하는 것을 조절할 수 있다.
주의) 값을 낮게 잡으면 CPU 점유율이 올라가는 단점이 있다.
```md
jQuery.fx.interval = 1000; 
$("button").click(function(){ $("div").toggle( 3000 ); });
//3초에 1000 프래임
```
### .jQuery.speed()
어떤 함수의 속도를 조절할 수 있다.
```md
jQuery.speed = 3000; 
$("button").click(function(){ $("div").addClass('active') });
```
### .stop()
요소에 해당하는 애니메이션 효과를 그 즉시 종료시킬 수 있다.
```md
$( "#go" ).click(function() {
  $( ".block" ).animate({ left: "+=100px" }, 2000 );
});
$( "#stop" ).click(function() {
  $( ".block" ).stop();
});
```

## Fading
### .fadeIn()
요소를 서서히 나타나게 할 수 있다.
```md
$( "#ref_fadeIn").finish('fast'); // 빠르게 나타나기
```
### .fadeOut()
요소를 서서히 사라지게 할 수 있다.
```md
$( "#ref_fadeOut").finish('slow'); // 빠르게 사라지기
```
### .fadeTo()
투명도를 조절하여 움직임을 만들어 낼 수 있다.
다른 효과 함수와 달리 반드시 duration을 명시 해 주어야 한다.
```md
$( "#ref_fadeTo").fadeTo(1000, 0.5); // 1초 동안 0.5(50%)만큼의 opactiy로 처리된다
```
### .fadeToggle()
toggle()과 비슷한 기능으로 서서히 나타났다 사라졌다를 반복 할 수 있다.
```md
$( "#ref_fadeToggle").fadeToggle(200); // 빠르게 나타나기
```

## Sliding
### .slideDown()
요소를 서서히 펼칠 수 있다. (아래로 펼처짐)
```md
$( "#ref_slideDown").slideDown('fast'); // 마찬가지로 속도 조절 할 수 있음
```
### .slideUp()
요소를 서서히 접을 수 있다.
```md
$( "#ref_slideDown").slideDown('slow'); 
```
### .slideDown()
요소를 서서히 접었다 폈다를 반복 할 수 있다.
```md
$( "#ref_slideToggle").slideToggle(500); 
```