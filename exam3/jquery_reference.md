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
