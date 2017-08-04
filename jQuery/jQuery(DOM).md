# jQuery DOM

### 부모태그와 자식태그
```js
$(function(){
/*
$(부모태그>자식태그) 부모태그 바로 밑에 있는 자식을 가리킴
$(부모태그 자식태그) 부모태그 밑의 자식태그를 찾을때(자손까지 포함)
$(부모태그+자식태그) 바로 인접한 형제태그
$(부모태그~자식태그) 바로 인접한 형제태그 뿐만 아니라 다른 관련된 태그까지 찾기

next()라는 함수는 바로 옆의 태그를 의미
append(자식태그)는 조건에 만족하는 것을 추가한다는 의미
 */
$("*").addClass("textstyle");
$("em+a").next().css("background-color","yellow").each(function(){
	$(".result1").append($(this))
    });
});
```

### 동적으로 속성을 추가하기
```js
$(function(){

//(1) 동적으로 속성을 추가 -> 객체명.속성=값
var object1={}
object1.name="임시";
object1.addr="서울시 강남구 대현빌딩";
object1.age="34";


//(2) $.extends(기존객체명,객체명,객체명,,,)
var object2={name:"테스트"}
$.extend(object2,{
    region:"서울시 강북구",
    age:23,});

//(2)출력 $.each(1.출력할 객체, 2.매개변수로 index와 value값을 갖는 함수)
var output="";
$.each(object2,function(key,item){
    output+=key+":"+item+"\n";
    });
alert(output);
});
```

### 이미지 속성을 동적으로 부여하는 방법
```js
$(function(){
//$("선택자").attr({속성명:속성값,속성명:속성값2,,})
//$("img").attr({width:200,height:200})
$("img").attr({width:function(index){return (index+1)*100},
			   height:function(index){return (index+1)*100}});

//특정태그의 속성값을 불러와서 화면에 출력
//형식) var 변수명=$("선택자").attr("속성명")
$("img").each(function(){
	var src=$($(this)).attr("src")
	alert(src)
});
});
```

### 배열을 이용해서 속성 적용하기
```js
$(function() {
//var 배열명=[요소값1,요소값2,,,]
var color = [ "red", "white", "purple" ]
var background = [ "gray", "pink", "yellow" ]
			
$("h1").css({
color:function(index){return color[index]},
background:function(index){return background[index]}
    });
});
```

### 태그추가
```
/*
$(A).appendTo(B) -> A를 B의 기존자식 뒤에 추가
$(A).prependTo(B) -> A를 B의 기존자식 앞에 추가
$(A).insertAfter(B) -> A를 B뒤에 추가 (자식에 추가 X)
$(A).insertBefor(B) -> A를 B앞에 추가 (자식에 추가 X)

$(A).append(B) -> B를 A의 기존자식 뒤에 추가
$(A).prepend(B) -> B를 A의 기존자식 앞에 추가
$(A).after(B) -> B를 A뒤에 추가 (자식에 추가 X)
$(A).befor(B) -> B를 A앞에 추가 (자식에 추가 X)
*/

```

### 이미지 옮기기
```js
$(function(){
	$("img").css("width",100);
		
	setInterval(function(){
	$("img").first().clone().appendTo("body");
	},1000)
	});
```

### each함수의 배열관리, 객체관리
```js
$(function() {
	//$.each() 단독으로 사용(배열관리, 객체관리)
	var array = [{name : "naver", link : "http://www.naver.com"}, 
				 {name : "daum", link : "http://www.daum.net"}, 
				 {name : "nate", link : "http://www.empas.com"},
				 {name : "google", link : "http://www.google.com"}]
	//형식) $.each(컬렉션(배열),처리해줄 함수명(index,value))
	$.each(array,function(index,item){
				
	});
});
```