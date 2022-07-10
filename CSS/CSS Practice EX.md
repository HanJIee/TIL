# 실습예제



#### 1. checkbox를 체크하면 div컨텐츠 안보이게 설정

```
<style>
	div{
		border: 1px solid gray;
		width:300px; height:300px; 
		overflow:hidden;
		
		/*객체의 움직임 속도를 정한다 초단위*/
		transition-duration:3s;
		opacity:1;
	}
	
	div>img{
		width: 100%; height:600px;
	}
	
	#chk:checked+div{
		height:0px;
		width: 0px;
		opacity:0; 
	}

</style>
</head>

<body>
<input type="checkbox" id="chk">클릭
<div>
	<img src="../img/01.jpg">
</div>
</body>
```



---

#### 2. 반응하는 이미지 글

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<!--                                                        0~10-->
<meta name="viewport" content="width=device-width, inital-scale=1"/>
<style>
	ul, li{
		margin:0; padding:0; list-style-type:none;
	}
	li{
		margin: 5px 0; background-color:lightblue; float: left; width:100%;
	}
	
	/*media쿼리를 이용하여 반응형 스타일 지정*/
	/*디스플레이 종류 : all, screen, print, tv, projection...*/
	
	@media all and (min-width:320px) and (max-width:600px){
		li{background-color: yellow;}
		img{display: block;}
	} 
	@media all and (min-width:601px) and (max-width:800px){
		li{background-color: pink;}
		img{display: none;}
	}
	@media all and (min-width:801px){
		li{background-color:orange; color: white;}
		img{display: block;}
	}
	
	
</style>
</head>
<body>
	<ul>
	<li>BMW 신형 2시리즈 액티브 투어러의 국내 출시가 임박했다. 딜러사에 따르면 신형 2시리즈 액티브</li>
	<li>투어러는 이달 중 출시되며, 218d 디젤 모델이 먼저 투입된다.</li>
	<li>218d 디젤 모델이 먼저 투입된다. 소형 MPV로 고급스럽게 변경된 실내가 특징이다.</li>
	<li>2시리즈 액티브 투어러는 지난 2014년 출시 이후 전 세계에서 약 50만대 이상이 판매됐다. </li>
	<li>2실내 공간 활용성과 BMW의 시그니처인 펀(FUN) 드라이빙이 결합된 모델이다.</li>
	<li>2시리즈 액티브 투어러의 구매자 중 80%가 BMW를 처음 접하는 고객이다.</li>
	<li><img src="../img/02.jpg"></li>
	</ul>
</body>
</html>
```

