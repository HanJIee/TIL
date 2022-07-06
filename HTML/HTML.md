# HTML

[TOC]

---

### #기본용어

---

#### 1.기본태크

```
<!DOCTYPE html>
```

HTML 문서를 지정하는 것

```
<html> </html>
```

웹페이지 시작-끝

```
<head> </head>
```

웹페이지의 정보 / 링크

```
<!-- 주석 --> [Ctrl] + [/]
```

주석문을 다는 부분 / 웹 화면에 보이지 X

```
<body> /body>
```

웹에 보이는 부분

```
<meta charset="UTF-8">
```

웹 페이지의 문자를 UTF-8로 지정하라

```
<title> </title>
```

웹 페이지의 타이틀을 나타내는 태크

```
<h1~6>
```

제목 태그 / 문서의 헤드라인으로 h6까지 사용할 수 있다. / block

```
<p> </p>
```

문단(단락) 태그 / block 

```
<br></br>
```

줄바꿈 태크

```
<b> </b>
```

글자 굵게

```
<strong></strong>
```

내용의 강조를위해 굵게 표시 / inline

```
<i> </i>
```

글자 기울이기

```
<em></em>
```

내용의 강조를위해 기울이기 표시 / inline



----

#### 1-2. <a>태그

웹페이지, 외부링크로의 이동(하이퍼링크) 만들때 사용하는 태그 / inline

```
▶기본
<a></a>
<a href="연결할 링크">이름</a>
```

```
<a href="연결할 링크" target="" title="" >이름</a>
```

**target** : _blank - 새로운 창 ,  _self  - 현재 창

**title** : 마우스를 올릴시 나타나는 글

```
▶ 이미지에 링크 걸기
<a href="../index.html">index</a> (파일)
<a href="주소" target="_blank">자동차 기사</a> (외부)
```

```
▶ 링크를 통한 다운로드
<a href="../downFile/mysql_demo.sql">다운</a>
<a href="../img/01.jpg" download>이미지 다운</a>
```

```
▶ 같은 페이지 다른위치 이동 (id를 통한 이동)
<a href="#a1">html이란?</a><br/>

<a id="a1">1. html이란?</a><br/>
<p>Hyper Text Markerup Language</p>
```



##### 1-2.1 <a_map>

```
▶1개의 이미지에서 여러곳의 링크 걸기
ex)
<img src="../img/jeju_map.jpg" usemap="#jejuMap"/>

<map name="jejuMap">
	<area shape="rect" coords="170,115,300,160" href="https://www.airport.co.kr/jeju/index.do" target="_blank" title="제주국제공항"/>
	
	<area shape="circle" coords="330,260,50" href="http://www.jeju.go.kr/hallasan/index.htm" target="_blank" title="한라산국립공원"/>
	
	<area shape="poly" coords="70,210,160,240,100,270,10,265" href="../index.html" target="_blank" title="한라산국립공원"/>
</map>
```

shape : 링크모양 (rect, circle, poly)
coords : 좌표 (x, y)



----

#### 1-3. <img>태그 

이미지를 넣을 때 사용 (1개) / 웹페이지의 이미지주소 , 다운로드한 이미지 모두 가능 / inline

```
▶ 기본
<img>
<img src="이미지 위치">
```

```
▶ 이미지 크기 조정
<img src="../img/02.jpg" width="200px" height="200px"/> (px)
<img src="../img/03.jpg" width="100%" height="300px"/> (%)
<img src="../img/001.jpg" alt="no"/> (no 이미지)
```



---

#### 1-4. 목록태그

##### 1-4.1  <ol>

순서가 있는 목록 / 번호 형식으로 순서를 매겨 목록을 만든다

**<li>  ul 태그와 ol 태그의 내부에서 사용되는 태그 / 들여쓰기 및 줄바꿈 기능이 있다**

```
▶ 기본
<ol>
<li>내용<li>
</ol>
```

```
▶ 속성
<ol type="a" start="5">
<li value="9">내용</li>
</ol>

type="a"  : 1, a, A, i, I
start="5" : 시작하는 번호를 지정
value="9" : 특정 목록의 번호를 지정
```



##### 1-4.2 <ul>

순서가 없는 목록 / 점이나 사각형 등의 도형이  붙는다

```
▶ 기본
<ul>
<li>내용<li>
</ul>
```

```
▶ 속성
<ul type="square">
	<li>HTML</li>
</ul>

type : disk(안이 채워진 원), circle(안이 ql워진 원), square(안이 채워진 사각형)
```



##### 1-4.3 <dl>

정의 목록/용어를 사전적으로 정의하거나 설명할 때 사용

```
▶ 기본
<dl>
	<dt>용어</dt>
	<dd>정의나 설명</dd>
</dl>
```



---

#### 1-5. <table>태그

표를 만드는 태그

```
▶ 기본
<table>
	<tr>
		<th>섹션1</th>
		<th>섹션2</th>
	</tr>
	<tr>
		<th>섹션3</th>
		<th>섹션4</th>
	</tr>
</table>
```

```
▶ 속성
<table>
	<caption><h1>제목</h1></caption>
</table>

caption : table의 제목,  테이블의 위쪽 가운데 정렬
```

```
▶ 속성 rowspan, colspan
<tr>
	<td colspan="2">좌우 셀2</td>
</tr>

<tr>
	<td rowspan="2">상하 셀2</td>
</tr>


colspan <td>태그 사용, 열 확장 (좌우)
rowspan <td>태그 사용, 행 확장 (상하)
```



---

#### 1-6. 영역태그

```
<span></span>
```

영역을 나누는 태그 / 의미 X / inline(줄 단위 영역)

 

```
<div></div>
```

영역을 나누는 태그 / 의미 X / block(박스 형태 영역)

*div는 줄바꿈o span 줄바꿈x (하지만 display를 이용해 바꾸는것이 가능하다)



----

#### 1-7. 선택자 

```
class="" (.)
```

<요소 class=" 이름 ">

그룹을 설정하고 속성을 부여 / 여러 개의 값 가능 

```
id="" (#)
```

한가지만 설정하고 속성을 부여 / id의 값은 딱 한 번만 중복 불가

- **id 선택자> class 선택자> 태그 선택자 순**



---

#### 1-8. <iframe>태그

웹브라우저 내에 또다른 프레임, 또 다른 HTML페이지 삽입 가능

```
▶ 기본
<iframe src="주소"> 대체 내용</iframe>
```

```
▶ 속성
<frameborder="0" scrolling="no">

frameborder : 테두리 표시 (0 -> 없음)
scrolling : 스크롤바 유무
```



----

#### 1-9. <audio>태그

 음악이나 오디오 같은 사운드 정의 사용

```
▶ 기본
<audio controls>
	<source src="../audio/music.mp3" type="audio/mp3">
	<source src="../audio/music.ogg" type="audio/ogg">
</audio>

 controls : 컨트롤바 표시
```

```
▶ 속성
loop="2"

loop : 반복
```



----

#### 1-10.<video>태그

 비디오 정의 사용

```
▶ 기본
<video controls>
	<source src="../video/movie.mp4"/>
</video>
```

```
▶ 속성
poster="../img/01.jpg"(경로)

poster : 재생 버튼을 누르기 전 표시할 이미지
```



---

#### 1-11.<meta>태그

메타데이터 정의 사용

base, link, script, style, title요소와 같은 다른 메타데이터 관련 요소들이 나타낼 수 없는 다양한 종류의 메타데이터를 제공할 때 사용

```
▶ 속성
<meta name="description" content="이 페이지에 대한 설명을 기술한다"/>
<meta name="keywords" content="컴퓨터,it,ai,자바">
<meta name="author" content="hong gildong">
<meta http-equiv="refresh" content="10">
<meta http-equiv="Refresh" content="5; https://www.naver.com/"/>

- name 속성
	description : 이페이지에 대한 설명을 기술
	keywords : 검색엔진에 검색되는 단어들...
	author : 작성자
- http-equiv속성
	refresh : 새로고침(초단위), reloading...
	Refresh : 일전시간이 되면 page를 자동으로 이동한다
```



---

#### 1-12.<form>태그와 사용

사용자가  웹 페이지에서  서버로 데이터를 전송 / 로그인 창, 회원가입

```
<form method="get"  name="a" action="write.jsp"> </form>

name : 폼의 이름
method : 전송방식(get, post)
action : 서버페이지 파일명(url)
```

```
아이디 : <input type="text" name="userid" size="30" value="gugu" maxlength="10" 		 			placeholder="아이디를 입력하세요" required/>

비밀번호 : <input type="password" name="userpwd" placeholder="비밀번호 입력"/>

value : 초기값
maxlength : 최대글자수 
require : 필수 입력 필드 지정
placeholder : 힌트표시/입력시 사라짐
```

```
파일첨부 : <input type="file" name="filename"/>
체크박스 : <input type="checkbox" name="hobby" value="등산"/>등산
		  <input type="checkbox" name="hobby" value="쇼핑" checked/>쇼핑
라디오버튼 : <input type="radio" name="gender" value="M"/>남
		   <input type="radio" name="gender" value="F" checked/>여		  
		    
checked : 미리 선택될 <input> 요소 명시
```

```
관심분야 : <select name="interest" size="4" multiple>
				<optgroup label="프론트엔드">
						<option>HTML5</option>
						<option>CSS3</option>
						<option>JAVASCRIPT</option>
						<option>JQUERY</option>
				</optgroup>
				<optgroup label="백엔드">
						<option>JSP</option>
						<option>SPRING</option>
				</optgroup>	
		</select>

<select> 태그
드롭다운 리스트 정의

<option> : 리스트의 옵션
<optgroup> : 옵션들의 그룹을 정의

size : 요소의 수 명시
multiple : 둘 이상의 값을 입력
```

```
<textarea name="intro" cols="50" rows="5">ddddd</textarea>

<textarea> : 여러줄의 긴 내용을 입력하는 것이 가능
cols, rows : 너비, 높이
```

```
date : <input type="date" name="date1"/>date1  
datetime-local : <input type="datetime-local" name="date2"/>  
month : <input type="month" name="date3"/>  
week : <input type="week" name="date4"/>  
color: <input type="color" name="color"/>  
number : <input type="number" name="num" min="0" max="20" step="5"/>  
range : <input type="range" name="num2" min="1" max="10" step="2"/>  
```

```
<input type="submit" value="등록"/>  ▶서버전송 버튼
<input type="button" value="등록"/>  ▶ 
<input type="reset" value="다시쓰기"/>  ▶ 리셋
<input type="image" src="../img/button.png"/>  ▶ 
```



▶type

- `text`: 일반 문자
- `password`: 비밀번호

- `file`: 파일 업로드

- `checkbox`: 다수를 선택 
- `radio`: 한개만 선택
- `date`:연월일
- `datetime-local`:연월일시분초
- `month`:연월
- `week:`연주
- `color`:색상표
- `number:`숫자조절 화살표
- `range`:숫자조절 슬라이드 막대
- `submit`: 서버전송 버튼
- `button`: 이벤트를 발생시킬수 있다 submit차이 있음
- `reset`: 리셋
- `image`:submit 버튼 대신 사용할 이미지