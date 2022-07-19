# jquery Practice EX



style/body 없이 이미지 위치 잡기

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script>
	$(function() {
		$("body").css("margin","0px");
		
		
		$("body").append("<div id='pinkDiv'/>");
		$("#pinkDiv").css("height","40px").css("background-color","rgb(238,135,152)");
		
		$("body").append("<div id='blueDiv'/>");
		$("#blueDiv").css("height","22px").css("background-color","rgb(84,174,200)");
		
		//이미지추가
		$("body").append("<img src='../img/title_layer.gif'/>");
		
		var file = ['glass1.gif','glass2.gif','glass3.gif'];
		var tag="";
		file.map(function(value, idx) {
			tag +="<img src='../img/"+value+"'/>"
		});
		$('body').append(tag);
		
		$("img").css("position","absolute");
		$("img:first").css("top", "0px");
		
		$("img").eq(1).css("left","310px").css("top", "60px");
		$("img").eq(2).css("left","450px").css("top", "100px");
		$("img:last").css("left","380px").css("top", "140px");
	});
	
</script>
</head>
<body>
</body>
</html>
```



---



마우스 오버/아웃 팝업 메뉴 만들기

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<style>
	body, ul, li{margin:0; padding:0; list-style-type:none;}
	
	.logo a:link, .logo a:visited{text-decoration:none; color:#000;}
	.logo a:hover{text-decoration: none; color:#f00;}
	
	.submenu, a:link, a:visited{ text-decoration:none; color:#333;}
	.submenu a:hover{text-decoration:none; color:#333; font-weight:bold;}
	
	.container{
		width: 1000px; margin:0 auto;
	}
	/*로고*/
	.logo{
		height:100px; line-height:100px; text-align:center; font-size:3em;
	}
	
	/*메인메뉴*/
	.popmenu{
		height:50px;
		border-top:2px solid #333;
		border-bottom:1px solid #333;
	}
	
	.popmenu>li{
		float:left; width:20%; height:50%; line-height:50px; text-align:center; 
	}
	
	/*서브메뉴*/
	.popmenu>li>ul{
		background-color: white;
		position: relative;
		display:none;
	}
	
	.section>img{width:100%;}

</style>
<script>
	$(function() {
		//팝업메뉴
		$(".popmenu>li").hover(function() {
			//메인메뉴가 마우스 오버일때
			$(this).children('ul').css('display','block');
		}, function() {
			//메인메뉴가 마우스 아웃일떄
			$(this).children('ul').css('display','none');
		});
	});
</script>
</head>
<body>

<div class="container">
	<!-- 로고 -->
	<div class="logo"><a href="#">GLRLSDAILY</a></div>
	<ul class="popmenu">
	  <li>
	  	<a href="#">Outer</a>
	    <ul>
	      <li><a href="#">가디건</a></li>
	      <li><a href="#">가디건&점퍼</a></li>
	      <li><a href="#">베스트</a></li>
	      <li><a href="#">코트</a></li>
	      <li><a href="#">세일</a></li>
	    </ul>
	  </li>
	  
	  <li>
	  	<a href="#">Top</a>
	    <ul>
	      <li><a href="#">Tee</a></li>
	      <li><a href="#">Cami</a></li>
	      <li><a href="#">Knit</a></li>
	      <li><a href="#">shirt & Blouse</a></li>
	    </ul>
	  </li>
	 
	  <li>
	    <a href="#">Dress</a>
	    <ul>
	      <li><a href="#">All</a></li>
	      <li><a href="#">바캉스룩</a></li>
	      <li><a href="#">Set</a></li>
	    </ul>
	  </li>
	  
	  <li>
	    <a href="#">Bottom</a>
	    <ul>
	      <li><a href="#">레깅스</a></li>
	      <li><a href="#">힐링투엘브</a></li>
	      <li><a href="#">히든밴딩시리즈</a></li>
	      <li><a href="#">스커트</a></li>
	      <li><a href="#">팬츠</a></li>
	    </ul>
	  </li>
	 
	  <li>
	  	<a href="#">Summer</a>
	    <ul>
	      <li><a href="#">HOLI스윕웨어</a></li>
	      <li><a href="#">at 22ºC</a></li>
	    </ul>
	  </li> 
	</ul>
	<div class="section">
		<img src="../../img/03.jpg"/>
	</div>
</div>
</body>
</html>
```



---



글쓰기 에티터 이용

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<!-- https://ckeditor.com/ckeditor-4/download/ -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="//cdn.ckeditor.com/4.19.0/full/ckeditor.js"></script>
<script>
	$(function() {
		//textarea에 ckeditor 셋팅하기
		CKEDITOR.replace('content');
		
		$("#boardFrm").submit(function() {
			//제목이 입력여부
			if($("#subject").val()==""){
				alert("글제목을 입력하세요");
				return false;
			}
			
			//글내용 입력여부
			//ckeditor 셋팅 textarea의 값을 가져오는 함수
			if(CKEDITOR.instances.content.getData() ==""){
				alert("글내용을 입력하세요");
				return false;
			}
			console.log(CKEDITOR.instances.content.getData());
			return true;
			
		});
	});
</script>
</head>
<body>
<h1>편집기</h1>
<form method="post" id="boardFrm" action="aaa.jsp">
<ul>
	<li>제목</li>
	<li><input type="text" name="subject" id="subjext"></li>
	<li>글내용</li>
	<li><textarea name="content" id="content"></textarea></li>
	<li><input type="submit" value="글등록"></li>
</ul>
</form>
</body>
</html>
```

