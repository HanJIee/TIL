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

#### 1-4. 영역태그

```
<span></span>
```

영역을 나누는 태그 / 의미 X / inline(줄 단위 영역)

 

```
<div></div>
```

영역을 나누는 태그 / 의미 X / block(박스 형태 영역)

*div는 줄바꿈o span 줄바꿈x (하지만 display를 이용해 바꾸는것이 가능하다)

 

**class(.)**

<요소 class=" 이름 ">

그룹을 설정하고 속성을 부여 / 여러 개의 값 가능 

**id(#)**

한가지만 설정하고 속성을 부여 / id의 값은 딱 한 번만 중복 불가

- **id 선택자> class 선택자> 태그 선택자 순**