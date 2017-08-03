# jQuery


부모와 자식태그 관계 정리
```js
//부모태그 > 자식태그->부모태그 바로 밑 자식태그를 선택할때 사용
//부모태그  자식태그-> 부모태그 밑의 모든 자손태그
//부모태그+자식태그->바로 옆의 태그를 찾을때 사용
$("body > div").css("border","3px solid navy");
$("body div").css("border","3px solid navy");
$("span+a").next().css("font-size","100pt"); // next() 현재항목의 다음항목을 의미
```

속성선택자
```js
$(function(){
/*
선택자 속성 설명
요소[속성명] 특정 속성을 가진 태그를 찾을때 사용
요소[속성명=값] 속성값이 일치하는 태그를 찾아라
요소[속성명!=값] 속성값이 일치하지않는 태그를 찾아라
요소[속성명^=값] 지정한 값으로 시작하는 태그를 찾아라
요소[속성명|=값] 지정한 값을 찾거나 지정한 글자- 태그를 찾아라
요소[속성명$=값] 지정한 값으로 끝나는 태그를 찾아라
요소[속성명*=값] 지정한 값을 포함한 태그를 찾아라
요소[속성명~=값] 지정한 값을 단어로서 포함하는 태그를 찾아라(단어중심)
*/
$("button[name]").html("변경됨");
$("input[type=text]").val("hello jQuery!");
$("input[type!=text]").val("부정");
$("div[id^=content-]").css("background","green");
$("div[id|=content]").css("background","blue");
$("input[name~=한국]").css("background","yellow");
$("input[id*=한국]").css("background","red");
$("div[id$=2]").css("background","brown");
});
```
입력양식 속성 선택자
```js
$(function(){
/*
입력양식에 관련된 속성 선택자
요소:button -> input태그중에서 type속성이 button인 경우
요소:reset(초기화), 요소:submit(전송)
요소:text -> type속성이 text인 경우
요소:checkbox
요소:file(파일첨부)
요소:image, 요소:password, 요소:radio
*/
//$("input[type=button]").val("회원가입");
$("input:checked").attr("checked",false);
$("input:disabled").attr("disabled",false);
$("input:text").val("값을 입력하세요")
$("input:password").css("background","pink").val("1234");
$("input:button").val("회언가입");
});
```