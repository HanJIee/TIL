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

