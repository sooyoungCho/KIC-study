# jQuery DOM
### addClass
스타일적용시 클래스명으로 스타일을 적용 시킬 수 있다.
```js
//addClass(스타일클래스명)
$(function(){
    $("h1:first").addClass("high_light_0")
});

//addClass(익명함수)
$('h1').addClass(function(index){ //각 태그를 구분하는 인덱스번호
    return 'high_light_'+index;
});

// <> removeClass(해제시키고자 하는 클래스명)
```