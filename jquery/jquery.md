# jquery

이벤트 기반 자바 스크립트 라이브러리

jquery.com -> 다운로드 -> cdn링크로 이동

---



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



---

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

---

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

---

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

---

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

---

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


​	
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

---

$(()=>{
		▣ before() : 선택자 이전에 객체를 추가
		$('#i').before("<li><img src='../img/02.jpg'></li>");
		▣  insertBefore() : 선택자 이전의 객체를 추가
		// 내용          선택자
		$("<li><img src='../img/03.jpg'></li>").insertBefore('#i')
		

​		▣ after() : 선택자 다음에 객체를 추가
​		$('#i').after("<li><img src='../img/04.jpg'></li>");
​		▣ insertAfter() : 선택자 다음에 객체를 추가
​		$("<li id='copy'><img src='../img/05.jpg'></li>").insertAfter('#i')
​		

​		▣ append() : 선택자의 내용중에 제일 마지막에
​		$('ul').append("<li><img src='../img/banner.JPG'></li>");
​		▣ appendTo() : 선택자의 내용중에 제일 마지막에
​		$("<li><img src='../img/logo.png'></li>").appendTo('ul');
​		// html()   $('ul').html(<img src='../img/03.jpg'></li>)
​	

​		▣ prepend(), prependTo() : 선택한 요소 제일 처음에 추가
​		$('ul').prepend("<li><img src='../img/boutton.png'></li>");
​		$("<li><img src='../img/jeju_map.jpg'></li>").prependTo('ul');
​		

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

---

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

---

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


​		
	});



</script>

---


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

​		
		//one() : 이벤트가 한번만 발생
		$('h2').one('click',function(){
			$(this).addClass('s2');
		}); 


​		
	});

</script>

---

