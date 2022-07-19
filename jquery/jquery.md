

# jquery

이벤트 기반 자바 스크립트 라이브러리

jquery.com -> 다운로드 -> cdn링크로 이동

---

### #1.활용

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>

<script>
	var a;
	//alert("aaaa");
	function f() {
		var b;
	}

	//jquery:document가 로딩이 완료되면 ready이벤트에 의해 jqery가 실행된다
	//선택자      이벤트  실행문
	
	▣ $(document).ready(function() {
		//실행문;
		alert("jquery 실행됨")
	}); 

	▣ jQuery(document).ready(function() {
		alert("jquery(cocument) 실행됨");
	}); 

	▣ $(function() {
		alert("제이쿼리 실행됨..."); -> 많이사용
	});

</script>
```

---

```
<script>
	$(function() {
		//jquery에서 스타일시트 적용하기
		▣태그 선택자   속성,속성값         background-color:red, backgroundColor="red"
		$("body").css("background-color","#ddd");
		▣클래스 선택자
		$(".c1").css("border","1px solid red");
		$("#t1").css("background-color","lightblue");

		▣jquery에서 html속성 제어하기
		$("img").attr("src","../img/03.jpg");
		$("#txt").attr("value","홍길동");
		
		//		readonly,checked,selected,disabled,controls...
		$("#txt").prop("readonly", true);
		
	});

</script>
```

---

```
<script>
	$(function() {
		//인접선택자
		//모든선택자(*), 태그선택자('img'), 아이디선택자('.i'), 클래스선택자('#i') 자손선택자('a>b') 후손선택자('a b')
		
		▣childen():자손을 선택한다
	$("div").children('.one').css('background', 'pink');
	▣next() : 선택자의 다음 객체를 선택한다
	$("div").next().css('color', 'red');
	▣prev(): 선택자의 이전객체를 선택한다
	$("img").prev().css("border","2px solid green").css("margin", "50px");
	▣parent() : 부모선택자
	$("img").parent().css('background', 'lightblue');	
	▣sibling() : 형제 선택자
	$('h2').sibling().css("color", "yellow");
	
	$('div').next().attr("title", "놀러가자~~~");
	
});
	</script>
```

---

```
<script>
	$(function() {
		▣위치선택자 first last even odd
		$("#menu>li:first").css('color','red');//첫번째
		$("#menu>li:last").css('color','green');
		$("#menu>li:even").css('background','lightblue');//0 1 2 3 4 5 6
		$("#menu>li:odd").css('background','pink');

		$("#menu>li:nth-last-of-type(3)").css('border','2px solid red');
		$("#menu>li:nth-child(3n)").css('font-size', '1.5em')//1 2 3 4 5 6
		
		▣li태그의 부모중 자식이 1개인 li를 선택한다
		$("li:only-child").css('background-color','yellow');
		
		▣index를 이용한 선택
		$("#menu>li").slice(3).css('color','blue');//index 3부터 끝까찌 선택자
		$("#menu>li").eq(2).css('background','orange');//index가 2인 위치를 선택
		
		▣lt() :less than, gt() : great htan
		$("#menu>li:lt(5)").css('font-size', '2em').css('color','cyan'); //자신빼고
		$("#menu>li:gt(3)").css('color','#f00');//자신다음
		
	});

</script>
```

---

```


<script >
	function jsFunction() {
		alert("클릭")
	}
	$(function() {
		$('li').css("hi")
		▶속성선택자



		▣a태그에 title속성이 있으면 선택
		$('a[title]').css("background-color","yellow");
		
		▣속성값으로 선택하기
		$('a[href="http://www.naver.com"]').css("borord","2px solid red");
		
		▣^ 특정값으로 시작하면
		$('a[href^="http://"]').css("padding","20px").css("border","1px solid blue");
		
		$('a[href$="com"]').css("background-color","orange");
	})

</script>
```

---

```
<script>
	$(function() {
		▶상태선택자
		▣ :text -> 속성값이 text인 캑체를 선택한다
		$(':text').css("background-color","green");
		▣ :checked -> 속성에 checked 설정되어있으면 선택
		$(':checked').css("width","40px").css("height","40px")//.prop("checked",false);
		▣ :selected -> 속성에 selected 설정되어있으면 선택
		$(':selected').css("background","orange")//.prop('selected',false);

		▶컨텐츠선택자
		▣ contains() : 특정한 문자가 포함되어 있으면 선택한다
		$("p:contains('하드코어')").css('background-color','pink');
		▣ has() : 특정태크가 포함된 경우를 선택한다
		$("p:has('b')").css('color','green');
		▣not() : 특정선택자 제외한 나머지
		$("p:not(:first)").css('font-weight','bold');
		▣ closest() : 조상선택자
		$('b').closest('div').css('border','4px solid red');
		▣ filter() 
		$('p').filter('.c1').css('color','orange');
		
		▣contents() : 특정태그의 하위내용이 다른 태그에 포함된 경우 하위태그를 선택한다
		$('p').contents().css('background-color','blue');
		
		▣selsctdeIndex : 선택된 option의 index를 구한다
		//document.getElementById("username").value=""; ->js
		$('#username').val($('#site').prop("selectedIndex")) ; 
		
		if($('#tel').val()==""){
			alert("전화번호를 입력하세요")
		}
	});

</script>
```

```
<div>
	<form>
		이름 : <input type="text" name="username" id="username"/><br/>
		연락처 : <input type="text" name="tel" id="tel"/><br/>
		사용자 동의 여부 : <input type="radio" name="accept" value="yes"/>동의
					   <input type="radio" name="accept" value="no"/>동의안함<br/>
		자주가는 사이트 : <select size="4" id="site">
						<option>==선택안함</option>
						<option>네이트</option>
						<option selected="selected">다음</option>
						<option>네이버</option>
					  </select><br/>
		<input type="submit" value="등록"/>
	</form>
</div>
```

---

```
<style>
	.c1{
		border: 2px solid red; width: 200px; height: 200px; }
	.c2{
		border: 2px solid blue; width: 200px; height: 200px; }
	.c3{
		border: 2px solid green; width: 200px; height: 200px; }
	.c4{
		border: 2px solid orange; width: 200px; height: 200px; }
</style>
<script>
	$(()=>{
		//html() : 특정개체에 html태그를 추가한다  => innerHTML
		var tag = "<a href=''>다음</a>을 클릭하시면 페이지가 이동합니다."
		$('result').html(tag);

		console.log( $('#result').html() );
	
		▣ text() : 특정캑체의 문자를 추가한다
		var tag2 = "<div>text()속성 연습중</div>";
		$("#result").text(tag2);
		
		console.log( $('a').text() );
		
		$('h2').children('a').attr('href','http://www.naver.com');
		$('a').removeAttr('href');
		$('h1').removeAttr('id');
		
		▶클래스 handler
		스타일시트의 클래스 조작하는 방법
		▣addClass() : 클래스 추가
		$('#lst>img').addClass('c1');
		$('#lst>img').addClass('c2');
		
		▣removeClass() : 클래스 삭제
		$('#lst>img').removeClass('c2');
		
		▣짝수번째 :c3  홀수번째 :c4
		$('#lst>img:even').addClass('c3');
		$('#lst>img:odd').addClass('c4');
		
		▣toggleClass() : 클래스 있으면 지우고 없으면 추가
		$('#lst>img').toggleClass('c3');
		
		▣hasClass() : 클래스가 존재하는지 유무확인(true, false)
		var h = $('#lst>img:first').hasClass('c1');
		console.log(h)
		$('h1').text(h+"");
		
		▣val() : 폼의 value를 구하거나 셋팅한다
		//html() text() attr() prop()
	
	});

</script>
```



---

```
$(()=>{
		▣ before() : 선택자 이전에 객체를 추가
		$('#i').before("<li><img src='../img/02.jpg'></li>");
		▣  insertBefore() : 선택자 이전의 객체를 추가
		// 내용          선택자
		$("<li><img src='../img/03.jpg'></li>").insertBefore('#i')
		

		▣ after() : 선택자 다음에 객체를 추가
		$('#i').after("<li><img src='../img/04.jpg'></li>");
		▣ insertAfter() : 선택자 다음에 객체를 추가
		$("<li id='copy'><img src='../img/05.jpg'></li>").insertAfter('#i')
		

		▣ append() : 선택자의 내용중에 제일 마지막에
		$('ul').append("<li><img src='../img/banner.JPG'></li>");
		▣ appendTo() : 선택자의 내용중에 제일 마지막에
		$("<li><img src='../img/logo.png'></li>").appendTo('ul');
		// html()   $('ul').html(<img src='../img/03.jpg'></li>)
	

		▣ prepend(), prependTo() : 선택한 요소 제일 처음에 추가
		$('ul').prepend("<li><img src='../img/boutton.png'></li>");
		$("<li><img src='../img/jeju_map.jpg'></li>").prependTo('ul');
		

		▣ clone() : 요소 복사하기 ->사용 한번만 항수있다
		var element = $('#copy').clone();
		element.attr("id","copy2");
		$('ul').prepend(element);
		
		▣empty() : 선택자의 내용을 지우기 (내용만)
		$("#copy").empty();
		▣remove() : 선택자의 내용을 지우기
		$("li:first").remove();
	
		▣replaceAll(), replaceWith() : 선택자를 다른 객체로 지환
		$("<h1>replaceAll</h1>").replaceAll("#copy");
		$("#i").replaceWith("<h1>replaceWith</h1>");
		setInterval('imgMove()',1000);
	});
	
	function imgMove() {
		$("li:first").appendTo("ul")
	}

</script>
```

---

```
<script>
 	$(function() {
	 ▶객체 감싸기
		▣ wrap() : 선택자를 특정태그로 각각 감싼다
 		$('.c1').wrap("<h1/>");



		▣wrapAll() : 선택자를 한번에 감싼다
		$('.c2').wrapAll("<div/>");
		▣wrapInner() : 선택자의 안쪽을 특정태그로 묶는다
		$('.c2').wrapInner("<b/>");
		
		▣unwrap() : 선택자의 부모를 지운다
		$('.c2').unwrap();
		
		▣esch() : 여러개의 객체를 순차적으로 적용(반복처리)
		//           idx=0 1 2 3 4 5 6   obj=li li li li li...
		$("#list>li").each(function(idx, obj) {
			$(obj).html("<li>each()함수를 이용한 반복실행...("+idx+")</li>");
		});
		
		▣map():배열을 이용한 반복실행
		var arr=['달리기','걷기','마라톤','사이클','스키','등산'];
		var tag = "<select>";
		//배열명.map(function(data, index));
		arr.map(function(data, idx) {
			tag +="<option>"+data+"("+idx+")</option>";
		});
		
		tag += "</select>";
		//$('body').prepend(tag);
		$('h1:first').before(tag);
	});

</script>
```

---

```
▶jquery 이벤트 종류
		//onclick. onmouseover. onmouseout......
		//onkeyup, onkeydown....
		

		▶ 이벤트 처리방법 1---------==----
		//h1에서 oncilck가 발생하면
		 $('h1').click(function() {
			//이벤트 발생시 실행되는 코드
			$("body").prepend("h1태크를 클릭하였습니다.");
			
			// this : 이벤트가 발생한 객체
			$(this).css("background","lightblue");
			$(this).text( $(this).text()+ "★" );
		}); 
		
		▶ 이벤트 처리방법 2---------------
		// on()  이벤트 종류, 실행할 함수
		 $("h1").on('click',function(){
			$(this).css("color", "red");
		}); 
		
		▶ 이벤트 처리방법 3----------------
		// h1에 마우스 오버를 하면 글자색 blue 마우스 아웃 글자색 green으로 변경
		 $('h1').on({mouseenter:function(){//마우스 오버
			$(this).css("color", "blue");
		}, mouseleave:function(){//마우스 아웃
			$(this).css("color", "green");
		}}); 
		
		▶ 이벤트 처리방법 4-----------------
		//1개의 요소에 2개이상의 이벤트를 한번에 작성하기
		 $("input").on('click focus',function(){
			$(this).css("background", "yellow");
		}); 
		
		▶ 이벤트 처리방법 5------------------
		//            이벤트종류,이벤트대상,실행함수
		 $(document).on('click','h1',function(){
			$(this).css("background","cyan");
			
		}); 
		
		// 이벤트 처리방법 6------------------
		 document.getElementById("i").addEventListener('click',function(){
			$(this).css('color', 'orange');
		}); 

	});

</script>
```

---

```
▶hover
<style>
	.s1{background-color: #f00; color:#fff;}
	.s2{background-color: #0f0; color:#f00;}
	.s3{background-color: #00f; color:#ff0;}
</style>
<script>
	$(function() {
		var cnt =0;
		$('h1').hover(function() {//오버시
			$(this).addClass('s1');
			cnt++;
			$("div").html("cnt="+cnt);
			if(cnt>5){
				$(this).off();//이벤트 중지
			}
		}, function() {//아웃시
			$(this).removeClass('s1');
		});

		//one() : 이벤트가 한번만 발생
		$('h2').one('click',function(){
			$(this).addClass('s2');
		}); 

	});

</script>
```

---

```
▶ trigger
<script>
	$(function() {
		var tag = "<img src='../img/02.jpg'/>"
		//이벤트 발생시 실행
		$("img:first").click(function() {
			$('body').append(tag);
		});
		
		//trigger() : 이벤트를 발생시킴
		//setInterval(), setTimeout()
		
		setInterval(function name() {
			//강제로 이벤트 발생시킴
			$("img:first").trigger('click');	
		}, 1000);
		
	});
</script>
```

---

```
▶effect
<script>
	$(function() {
		$("#hide").click(function() {
			//        사라지는 시간 : 'slow', 'fast', 'normal', 밀리초
			$("img").first().hide(4000, function() { //콜백함수
				//alert("종료됨");
			}); //폭 높이 투명도
		});
			
			▣ show() : 보여주기
			$("#show").on('click',function(){
				$("img:first").show(4000);
			});
			
			▣ toggle : 보여주기, 숨기기를 반복실행
			$(document).on('click','#toggle',function(){
				$('img').first().toggle(4000);
			});
			
			▣ 점점흐리게
			$("#fadeOut").click(function(){
				$("img").first().fadeOut(4000);
			});
			
			▣ 점점진하게
			$("#fadeIn").click(function(){
				$("img").first().fadeIn(4000);
			});
			
			▣ 흐리게 진하게 반복실행
			$("#fadeToggle").click(function(){
				$("img:first").fadeToggle(3000);
			});
			
			
			▣ 슬라이드
			$("#slideUp").click(function(){
				$("img").first().slideUp(3000);
			});
			
			$("#slideDown").click(function(){
				$("img:first").slideDown(3000);
			});
			
			$("#slideToggle").click(function(){
				$("img").first().slideToggle(3000);
			});
		});
</script>
</head>

<body>
<button id="hide">숨기기(hide)</button>
<button id="show">보여주기(show)</button>
<button id="toggle">숨기기,보여주기(toggle)</button>
<button id="fadeOut">점점흐리게(fadeOut)</button>
<button id="fadeIn">점점진하게(fadeIn)</button>
<button id="fadeToggle">(fadeToggle)</button>
<button id="slideUp">slideUp</button>
<button id="slideDown">slideDown</button>
<button id="slideToggle">slideToggle</button>
<hr/>
```

---

```
▶ animate
<style>
	div{float: left; width:126px; height:162px;}
	img{position:absolute;}
</style>
<script>
	$(function() {
		//animate(): 객체를 이동시킨다
		//animate({json형식으로 속성설정}, 속도)
		//        marginLeft, wigth, marginTop, opacity, marginRight
		$("img:first").animate({marginLeft:"800px",marginTop:"500px",opacity:0.3}, 5000)
					.delay(3000).animate({nargin:"10px", opacity:1});
		
		$("img:eq(2)").animate({marginLeft:"700px",marginTop:"400px"}, 5000);
		
		$("img:eq(1)").delay.animate({marginLeft:"900px",marginTop:"300px"}, 5000);
		
		
		$("img").mouseover(function() {
			$(this).stop();
		});
		
		
		$("img").mouseover(function() {
			//$(this).animate({marginLeft:"700px",marginTop:"400px"}, 5000);
		});
		
	});
</script>
```

---

```
▶ easing

<!--  
		easing종류 확인가능
		https://jqueryui.com/easing/ -> API documention
		jqueryui가 필요함
		jqueryui.com/download/all ->zip 압축해제

		1.jquery-ui-min.css 스타일 시트 연결
		2.jquery.min.js
		3.jquery-ui.min.js
-->

<link rel="stylesheet" href="/webApp/js_css/jquery-ui.min.css" type="text/css"/>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="/webApp/js_css/jquery-ui.min.js"></script>

<style>
	img{position:relative;}
</style>
<script>
	$(function() {
 	
		//easing : 움직이는 모양
		$("img").first().animate({marginLeft:"1200px"},6000,"easeOutBounce");
		$("img:eq(1)").animate({marginLeft:"1000px"},5000,"easeOutBack");
		
	});
</script>
```

---

### #2. plugin

```
▶ innerfade 사용해보기

<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="/webApp/js_css/jquery.innerfade.js"></script>
<style>
	ul, li{
		margin:0; padding:0; list-style-type:none;
	}
	#imgInner img{
		width:500px; height:400px;
	}
</style>
<script>
	$(function() {
		
		$("#imgInner").innerfade({
			animationtype : 'slide' // slide fade 기본fade
			,speed:3000 //slow fast normal 밀리초
			,timeout:5000 //쇼대기 시간
			,type : 'random' //random  sequence:기본  random_start 
		});
		
	});
</script>

```



```
▶ bxslider 사용해보기

<!--
	1.jquery
	2.easing
	3.bxslider 스크립드
	4.bxslider 스타일시트
	5.img 폴더 복사
 -->
 
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="/webApp/js_css/jquery.easing.1.3.js"></script>
<script src="/webApp/js_css/jquery.bxslider.js"></script>
<link rel="stylesheet" href="/webApp/js_css/jquery.bxslider.css" type="text/css">
<style>
	ul, li {margin:0; padding:0;}
	#imgSlider img {
		width: 800px; height: 400px;
	}
</style>
<script>
	$(function() {
		$("#imgSlider").bxSlider({
			mode:'horizontal' //화면전환 방식 'horizontal' 'vartical'  'fade'
			, sliderWidth : 800 //슬라이드 폭
			, sliderHeight : 450 //높이
			, speed : 3000
			,auto : true//자동시작
			,randomStart : true //랜덤시작
			, captions : true //title 속성값을 설명으로 표시 
			, infiniteLoop : false //반복여부
			, hideControlOnEnd : true //좌우 컨트롤보여주기 true 처음과 마지막표시안함
			
			
			, useCSS : false //easing 사용여부 true-사용안함
			,easing : 'easeOutElastic'
			//,onSliderLode : function(){ //슬라이드가 로딩이 완료되면 호출되는 콜백함수
			//	alert("콜백함수 실행됨")
			//}
			,onSlideAfter:function(){ //슬라이드가 움직인후 실행 콜백함수
				console.log("onSliderAfter 실행됨")
			}
		});
	});
</script>
</head>
<body>
<div>
	<ul id="imgSlider">
		<li><a href="http://www.nate.com"><img src="/webApp/img/01.jpg" title="네이트로 이동하기"></a></li>
		<li><a href="#http://www.naver.com"><img src="/webApp/img/02.jpg"  title="네이버로 이동하기"></a></li>
		<li><a href="#"><img src="/webApp/img/03.jpg" title="세번째 이미지 설명"></a></li>
		<li><a href="#"><img src="/webApp/img/04.jpg" title="네번째 이미지 설명"></a></li>
		<li><a href="#"><img src="/webApp/img/05.jpg" title="다섯번째 이미지 설명"></a></li>
		<li><a href="#"><img src="/webApp/img/06.jpg" title="여섯번째 이미지 설명"></a></li>
		<li><a href="#"><img src="/webApp/img/07.jpg" title="일곱번째 이미지 설명"></a></li>
		<li><a href="#"><img src="/webApp/img/08.jpg" title="여덟번째 이미지 설명"></a></li>
	</ul>
</div>
</body>
```



```
▶ Accordion 사용해보기

<!-- 
	1.accordionImageMenu.css
	2.jquery
	3.jquery-ui.min.js
	4.jquery.accordionImageMenu.js
 -->
 
<link rel="stylesheet" href="/webApp/js_css/accordionImageMenu.css" type="text/css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="/webApp/js_css/jquery-ui.min.js"></script>
<script src="/webApp/js_css/jquery.accordionImageMenu.js"></script>
<script>
	$(function() {
		$("#acc").AccordionImageMenu({
			position: 'horizontal' // 'horizontal' 'vertical'
			, openItem: 3 //기본선택 목록, index 위치의 내용이 크게 나옴
			, openDim : 500 //확장된 목록의 폭
			//, closeDim : 100 //닫힌목록의 크기
			
			//Width, height 'horizontal'일때는 높이만 적용 'vertical'은 폭만 적용
			//,width : 800
			,height : 500
			,duration : 3000 //전환속도
			, effect : 'easeOutBounce'
			, border : 1
			, color : "yellow"//배경
		});
	});
</script>
```



```
▶ dialog 사용해보기

<!-- 
	1.jquery-ui css
	2.jquery
	3.jquery-ui js
 -->
 
<link rel="stylesheet" href="/webApp/js_css/jquery-ui.min.css" type="text/css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="/webApp/js_css/jquery-ui.min.js"></script>
<style>
	#dialogOpen, #schedule{font-size: 2em; background: #ffd; text-align:center;}
	#schedule{background: #dff;}
	
	h2{text-align:center;}
	input[type=text], label{margin-bottom: 13px; padding:5px; width:95%;}
</style>
<script>
	$(function() {
		//일정등록 클릭시
		$("#dialogOpen").click(function() {
			//일정등록을 클릭하면 다이얼로그 탕 보이게 하기
			$("#dialog").dialog('open');
		});
		
		//다이얼 로그 
		$("#dialog").dialog({
			autoOpen: false //실행시 자동열림설정(true 기본)
			, buttons:{
				submit : function() {
					var name = $("#event-name").val();
					var date = $("#event-date").val();
					
					$("#schedule").append("<p>"+name+" : "+date+"</p>");
					
					$("#event-name").val('');
					$("#event-date").val('');
				},
				reset : function() {
					$("#event-name").val('');
					$("#event-date").val('');
				},
				close : function() {
					$("#event-name").val('');
					$("#event-date").val('');
					$('#dialog').dialog('close');
					
				}
			}
			
			, modal : true //창이 떴을떄 뒤에 창 작업 가능한가 불가능한가
		});
		
		//날짜입력박스 : datepicker셋팅
		$("#event-date").datepicker({
			dateFormat : "yy년 mm월 dd일" //y:년도 2자리  yy:년도 4자리 yy-mm-dd
			, numberOfMonths : 3
		});
	});
</script>
</head>

<body>
<div id="dialogOpen">일정등록</div>
<hr/>
<div id="schedule">일정이 표시되는 곳</div>

<!-- 다이얼 로그 창 -->
<div id="dialog" title="JQUERY UI Dialog">
	<h2>일정을 등록하세요</h2>
	<label for="event-name">일정이름</label> :
	<input type="text" id="event-name"/>
	<label for="event-date">날짜선택</label> :
	<input type="text" id="event-date"/>
</div>
</body>
```

