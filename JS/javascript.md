# javascript

### #기본용어

```
//주석
/*여러줄 주석*/

var, let, const
초기값에 의해서 대이터형이 정해진다. 초기갑을 설정하지 않은 경우 undefined

var i=12.5; //i라는 변수를 필요하면 다시 선언해도 된다
let k; //같은 블럭에서는 한번만 사용할수 있다
const x=10; //상수화된 변수 다른값 넣을수 x

▶출력
document.write();
```



```
▶외부 js연결
<script src="script.js"></script> 

alert("외부파일 스트립트 실행됨."); >알림창
var q = confirm("계속하시게습니까?") >확인알림창
var v = prompt("값을 입력해 주세요",10) > 입력알림창

▶활용예시
ocument.write("q=", q, '<br/>')
if(q){
		window.close();
	 }
	
	for(var i=2; i<=9;  i++){
		document.write(v, '*', i, '=', (v*i), '<br/>');
	}
```

```
▶js 스타일 제어하기

[예시코드]
<input type="txt" name="username" id="username" value="홍길동">
<div id="view"></div>
<img src="../img/03.jpg" width="100" height="100" id="i">

[활용]
ocument.getElementById("username").style.color="orange";

var dom = document.getElementById("view");
	dom.style.border = "1px solid red";
	dom.style.width = "300px";
	dom.style.height = "200px";

var name = document.getElementById("username").value;
	document.write("이름=" + name);
	document.getElementById("username").value= "이순신";
	document.getElementById("i").src="../img/02.jpg"
	
	document.getElementById("username").type="checkbox";
	(덮어 바꾸기 가능)
```

```
▶javascript에서 태그 삽입

var tag ="<h1>javascript에서 태그 삽입</h1>"
tag += "<ol><li>코스모스</li><li>해바라기</li></ol>";

document.getElementById("view").innerHTML = tag ;
```

```
▶함수 생성
함수는 호출하여야 실행됨 / 함수명([매개변수, 매개변수....])
function ABC() {}

[활용 - 구구단]
function gugudan(dan) {
	    var dan = document.getElementById("dan").value;
	    if(!isNaN(dan)){//숫자가 아닐때 true
		    var r = "<ul>"
		    for(var i=1; i<=9; i++){
				r+= "<li>"+dan+"*"+i+"="+(dan*i)+"</li>";
			}
			r +="</ul>"
				console.log(r);
			document.getElementById("result").innerHTML = r;
	    }else{
	    	document.getElementById("result").innerHTML = "숫자가 아닙니다";
	    }
	}
	
		var hap = function(a, b) {
  		var h = a+b;
		document.getElementById("result").innerHTML = h;
	}
  	
  	var cha = (a,b)=>{
  		var c = a - b;
  		console.log(c);
  	}
	
	
	
	
	
<input type ="text" id="dan">
<input type="button" value="클릭하세요" onclick="gugudan(6)"><br/>
<input type="button" value="합" onclick="hap(10, 20)">
<input type="button" value="차" onclick="cha(10, 20)">
<div id="result"></div>
<img src="../img/03.jpg">
```

```
▶문자열 처리 함수
function stringTest() {
		var str = "자바스크립트 문자열 처리 함수";
		
		var tag ="";
		
		tag += "lenght="+str.length;
		tag += "<br/>indexOf="+ str.indexOf("크");
		
		
		tag += "<br/>slice="+str.slice(2,8);
		tag += "<br/>substring="+str.substring(2,8);
		tag += "<br/>substr="+str.substr(2,8);
		
		tag += "<br/>replace" + str.replace("스크립트", "script");
		
		var str2 = "Hello! Javascript";
		tag += "<br/>toUpperCase"+ str.toUpperCase(str2);
		tag += "<br/>toLowerCase"+ str.toLowerCase(str2);
		
		tag += "<br/>concat" + str.concat(str2);
		tag += "<br/>charAt" + str2.charAt(3);
		tag += "<br/>charCodeAt" + str2.charCodeAt(3);
		
		var txtArr = str2.split("a");
		for(var idx = 0; idx<txtArr.length; idx++){
			tag += "<br/>txtArr["+idx+"]=" + txtArr[idx];
		}
		
		
		
		document.getElementById("view").outerHTML = tag;
		//outer 원래있던 태그 지우고 들어감
```

```
▶ Math함수
<script>
	var tag = "PI="+Math.PI;
	tag += "<br/>pow="+Math.pow(5,3);
	tag += "<br/>round="+Math.round(5.6);
	tag += "<br/>ceil="+Math.ceil(-5.6);
	tag += "<br/>floor="+Math.floor(-5.6);
	tag += "<br/>round="+Math.max(21,324,4,64,5.6);
	tag += "<br/>round="+Math.min(21,324,4,64,5.6);
	tag += "<br/>random="+Math.random();
	
	document.write(tag);
</script>
```

```
▶ 배열
배열의 크기를 지정하지 않아도 O / 데이터형다른 데이터를 하나의 배열에 보관 가능
	var arr = new Array();
	
	arr[2] = 150;
	arr[5] = "홍길동";
	arr[10]= 12.54;
	
	document.write("arr="+arr+"</br>");
	
	var arr2 = new Array(111, 222,333,"aaa","bbb");
	document.write("arr2="+arr2+"</br>");

	var arr3 = [23,5,12,"가나","다라"];
	document.write("arr3="+arr3+"</br>");
	
	▣배열에 데이터 추가하기 : 마지막에 값추가
	arr2.push("서울시 강남구");
	document.write("arr2="+arr2+"</br>");
	
	▣join : 문자연결하기
	var txt =arr2.join("/");
	document.write("arr2.join->"+txt+"</br>");
	
	▣pop :마지막테이터 삭제하기
	arr2.pop();
	document.write("arr2.pop="+arr2+"</br>");
	
	▣배열의 이동
	//shift(); 오른쪽데이터를 왼쪽으로 이동하고 0번째 index의 값은 지워진다
	//unshift();
	
	arr2.shift(); //111,222,333,aaa,bbb -> 222,333,aaa,bbb
	document.write("arr2.shift="+arr2+"</br>");
	
	arr2.unshift("서울시 영등포구"); // 111,222,333,aaa,bbb -> 서울시 영등포구,222,333,aaa,bbb
	document.write("arr2.unshift="+arr2+"</br>");
	
	▣Json(javascript odject notation)데이터 처리하기
	var jData = {username:"홍길동", tel:"010-1234-5678",
				email : {
						firstemail:'dsff12@nate.com',
						secondemail:'gred45@naver.com'
						},
				gugudan : function (dan) {
										var r="";
										for(var i=2; i<=9; i++) {
											r+=dan+"*"+i+"="+(dan*i)+"</br>"
										}
										return r;
								}
				};
		
	document.write("username->"+jData.username+"</br>");
	document.write("tel->"+jData.tel+"</br>");
	document.write("email->"+jData.email.firstemail, jData.email.secondemail+"</br>");
	document.write("tgugudan->"+jData.gugudan(9));
```

```.
▶배열 정렬
<script>
	function arraySortTest(){
		var numData = [36,43,74,86,23,-89,7,80];
		var txtData = ['tomato', 'apple', 'pineapple', 'peach', 'banana', 'orange', 'melon'];

	// Ascending Sort
	
	▣ 문자에대한 오름차순
	txtData.sort();
	document.getElementById("result").innerHTML = "txtData asc->" + txtData;
	
	▣숫자에 대한 오름차순
	numData.sort(function(x,y){return x-y;});
	document.getElementById("result2").innerHTML = "numData asc->" + numData;
	
	//Descending Sort
	
	▣문자에 대한 내림차순
	▣오름차순으로 정률후 역순으로 변경
	txtData.reverse();
	document.getElementById("result3").innerHTML="txtData desc->" + txtData
	
	▣숫자에 대한 내림차순
	numData.sort(function(a,b){return b-a});
	document.getElementById("result4").innerHTML = "numData desc->"+numData;
}
</script>
</head>
<body onload="arraySortTest();">
<h1>배열의 정렬</h1>
<div id="result"></div>
<div id="result2"></div>
<div id="result3"></div>
<div id="result4"></div>
```

```
▶현재시스템의 날짜와 시간정보 얻어오기
var setDateTime = function(){
		var now = new Date();
		
		document.getElementById("now").innerHTML = now;
		
		▣날짜변경
		var now1 = new Date("2022.10.04");
		var now2 = new Date(4842328645)//밀리초 1970년 1월1일 0시 0분 0초기준으로 계산된다.
		document.getElementById("result").innerHTML = now1 +"<br/>"+ now2;
		
		▣년 : getFullYear(), 월 : getMonth(), 일 : getDate()
		▣시 : getHours(), 분 : getMinutes(), 초 : getSeconds()
		▣요일 :getDay() -> 일요일부터 0~6
		
		var tag = now.getFullYear() + "-" + (now.getMonth()+1)+ "-" + now.getDate();
		tag +=" " + now.getHours() + ":" + now.getMinutes() + ":" + now.getSeconds();
		tag += "("+now.getDay()+")";
		
		document.querySelector("#view").innerHTML= tag;
	}
</script>
</head>
<body onload="setDateTime()">
<h1>날짜와 시간</h1>
<h1 id="now"></h1>
<div id="result"></div>
<div id="view"></div>
</body>
</html>
```

```
▶팝업창 띄우기
	▣1.새창에 띄울 파일명
	▣2.창이름:창이름이 없으면 새창에 반복적으로 만들어짐
	▣3.옵션:width,height,left, top
	var win;
	function openPopup() {
		win = window.open("popup.html", "win", "width=400px, height=600px, left=200, 			top=200px");
	
	▣ 중앙 위치 좌표 설정
		var x = screen.width/2 - win.outerWidth/2;
		var y = screen.height/2 - win.outerHeight/2;
	
		win.moveTo(x,y);
	}
	
	▣ 닫기
	function closePopup() {
		win.close();
	}
	
	▣ 창이동하기
	function windowMove() {
		⊙절대좌표
		win.moveTo(500,300);
		⊙상대좌표
		win.moveBy(-10,10);	
	}
	
	▣ 창의 크기를 변경
	function windowSize() {
		win.resizeBy(10,-10);
		
		⊙절대크기
		win.resizeTo(800, 400);
		⊙상대크기
		win.resizeBy(10, 10);
	}
	
	
```

```
▶ 좌표구하기
	function winInfor() {
		var txt = "";
		▣ 윈도우의 좌표구히기
		txt += "x좌표->"+window.screenX +"</br>"
		txt += "y좌표->"+window.screenY +"</br>"
		
		▣ 테두리와 제목을 초함한 폭과 높이
		txt += "outerWidth->" + window.outerWidth +"</br>"
		txt += "outerHeight->" + window.outerHeight +"</br>"
		
		▣ 테두리와 제목을 제외한 폭과높이
		txt += "innerWidth->" + window.innerWidth +"</br>"
		txt += "innerHeight->" + window.innerHeight +"</br>"
		
		▣ screen의 폭과 높이 구하기
		txt += "screen.width->"+ screen.width + "</br>"
		txt += "screen.height->"+ screen.height + "</br>"
		
		document.querySelector("#view").innerHTML= txt;
	}
	
	<body onload="openPopup(); winInfor();" >
    <h1>윈도우 내장 객체</h1>
    <input type="button" onclick="openPopup()" value="팝업창띄우기">
    <input type="button" onclick="closePopup()" value="팝업창닫기">
    <input type="button" onclick="windowMove()" value="창이동">
    <input type="button" onclick="windowSize()" value="창크기변경">
    <div id="view" style="border: 1px solid gray;"></div>
    </body>
```

```
▶setInterval

<script>
	▣ 움직이는 타이머
	function setTimer() {
		var now = new Date();
		
		var hour = now.getHours();
		var minute = now.getMinutes();
		var second = now.getSeconds();
		
		var nowTxt = "";
		if(hour<10){
			nowTxt+= "0";
		}
		nowTxt += hour+":"
		
		if(minute<10){
			nowTxt+="0";
		}
		nowTxt+=minute+":"
		if(second<10){
			nowTxt+="0";
		}
		nowTxt+=second;
		
		document.getElementById("clock").innerHTML = nowTxt;
	}
		▣ 움직이는 이미지
		var step=50;
		var left=0;
     function moveImage() {
		var img = document.getElementById("i").style;
		left = left + step;
		img.left = left+"px"
		if(left>500){
			step = -5;
		}
		if(left<0){
			step=5;
		}
	}
		
		var interval;
		▣ 움직이는 배경
		var y=0;
		function backMove() {
			y += 5;
			document.getElementById("b").style.backgroundPosition =  "0px " +y+ "px";
		}
		
</script>
<style>
	body{
		background: url(../img/04.jpg);
	}
	#i{width: 100px; height:100px; position: absolute; left: 0px; top: 0px;}
</style>
</head>

<!-- 성정한 시간간격으로 호출됨 : setinterval('호출할함수',밀리초)-->
<!-- 인터벌을 중지시킨다 : clearInterval() -->
<body onload="interval = setInterval('moveImage()',500); setInterval('setTimer()',1000); setInterval('backMove()',200);" id="b">
<img src="../img/03.jpg">
<h1 id="clock"></h1>
<img src="../img/02.jpg">
<img src="../img/01.jpg" id="i" onmouseover="clearInterval(interval)"
								onmouseout="interval=setInterval('moveImage()',100)">
</body>
</html>
```

```
▶ setTimeout 반복실행
<script>
var imgTag="";
var cnt=0;
function addImage(){
	cnt++;
	imgTag += "<img src='../img/03.jpg' width='100'/>"
	document.getElementById("imgView").innerHTML = imgTag;
	
	▣ 재귀호출
	var timer = setTimeout('addImage()',1000);
	if(cnt>10){
		clearTimeout(timer);//반복호출중지
	}
}
</script>
</head>
<body onload="addImage()">
<h1>setTimeout을 이용한 반복실행</h1>
<div id = "imgView"></div>
</body>
```

```
▶ 스크롤
<style>
	#content{
		width: 1000px;
		background-color: #ddd;
		margin: 0 auto;
	}
	#content>img{
		width: 100%;
	}
</style>
<script>
	var timer;
	function moveScroll() {
		▣절대위치 이동  x=left, y=top
		window.scrollBy(2,   10);
		
	}
	function scrollInfor() {
		▣상대위치 이동
		▣현재 스크롤의 위치
		console.log('y좌표',window.scrollY);
		console.log('x좌표',window.scrollX);
		console.log('y좌표', document.documentElement.scrollTop);
		
		console.log('높이',document.body.clientHeight);
		console.log('높이',document.body.scrollHeight);
	}
</script>

</head>
<body onload="scrollInfor(); timer = setInterval('moveScroll()',1000);">
	<div id="content" onmouseover="clearInterval(timer);" onmouseout="timer = setInterval('moveImage()', 500)">
		<script>
			for(var i=1; i<=4; i++){
				document.write("<img src='../img/0"+i+".jpg' onmouseout='this.src=\"../img/05.jpg\"' onmouseout='this.src=\"../img/0"+i+".jpg\"'/>");
			}
		</script>
	</div>
</body>
```

```
▶document

<body link="red" alink="green" vlink="orange">
<a href="https://www.daum.net">다음홈페이지</a>
<a href="https://www.nate.com">네이트홈페이지</a><br/>
<a href="https://www.jquery.com">제이쿼리홈페이지</a><br/>
<input type="text" name="userid" class="userid"><br/>
<input type="text" name="username" id="username"><br/>
<div style="background-color: #ddd;">
	
	<script>
		document.title = "자바스트립트에서 제목설정하기";
		document.write("location->"+document.location); //프로토콜, url, port, 경로, 파일명
		document.write("<br/>url->"+ document.URL);
		document.write("<br/>domain->"+ document.domain);
		document.write("<br/>lastModified->"+ document.lastModified);
		
		document.bgColor = "#afdged";
		document.write("<br/>bgColor->"+document.bgColor);
		
		▣링크 컬러설정
		document.linkColor = "yellow";
		document.write("<br/>linkColor->"+ document.linkColor+"<br/>vlinkColor->"+document.vlinkColor+"<br/>alinkColor->"+document.alinkColor+"<br/>");
	
		▣쿠키
		document.cookie = "값을 저장할 수 있다";
		document.write("cookie->", document.cookie);
		
		function domSelect() {
			document.getElementById("username").value="홍길동";
			document.querySelector("#username").value="세종대왕";
			
			document.getElementsByTagName("a")[1].title= "nate.com으로 이동합니다";
			document.getElementsByClassName("userid")[0].value="hong gildong";
		}
		domSelect();
	</script>
</div>
</body>
```

```
▶ location
<body>
<h1>location 내장객체</h1>
<script>
	document.write("protocol->"+location.protocol);
	document.write("<br/>hostname->"+location.hostname);
	document.write("<br/>port->"+location.port);
	
	document.write("<br/>host->"+location.host); //hostname+port
	
	▣location.reload();//현재페이지 재실행
	
	▣페이지 이동
	location.href = "https://www.nate.com";
	location.href = "../index.html";
</script>
</body>
```

```
```

