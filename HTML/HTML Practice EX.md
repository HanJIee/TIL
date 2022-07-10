# 실습예제



#### 1. 기본 홈페이지 레이아웃

```
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<style>
	body, ul ,li{
		margin:0; padding:0;
	}
	li{
		list-style-type: none;
	}
	header{
		background-color: pink;
		width:1200px;
		height:100px;
		margin:0 auto;
	}
	nav{
		height:40px;
		background-color: olive;
		color:white;
	}
	/*메뉴*/
	#mainMenu{
		width: 1200px;
		height:40px;
		margin:0 auto;
	}
	#mainMenu>li{
		float:left;
		width: 25%;
		height:40px;
		line-height:40px;
		text-align: center;	
	}
	main{
		width: 1200px;
		margin: 0 auto;
		background-color:  yellow;
		/*overflow:auto;*/
		position:relative;
	}
	#mainSection{
		overflow:auto;
	}
	main>#mainSection>*{
		float:left;
	}
	aside{
		width:150px;
		background-color:lightblue;	
	}
	section{
		width:1050px;
		background-color:lime;
	}
	footer{
		height:80px;
		background-color:#ddd;
		text-align: center;
	}
	/*배너*/
	#leftBanner{
		background-color:red;
		width:80px;
		height:200px;
		position:absolute;
		left:-80px;
		top:100px;
	}
	#rightBanner{
		background-color:blue;
		width:100px;
		height:300px;
		position:absolute;
		left: 1200px;
		top: 300px;
	}
</style>
</head>

<body>
	<header>
		로고, 로그인, 회원가입, 고객센터등 
	</header>
	
	<nav>
		<ul id="mainMenu">
			<li>메뉴1</li>
			<li>메뉴2</li>
			<li>메뉴3</li>
			<li>메뉴4</li>
		</ul>
	</nav>
	
	<main>
		<div id="mainSection">
			
			<aside>
				<h2>서브메뉴</h2>
				<ul>
					<li>11111</li>
					<li>11111</li>
					<li>11111</li>
					<li>11111</li>
				</ul>
			</aside>
			
			<section>
				<img src="../img/05.jpg">
			</section>
		</div>
		
	<!-- 배너 -->
	<div id="leftBanner"></div>
	<div id="rightBanner"></div>
	</main>
	
	<footer>
		푸터
	</footer>
</body>
</html>
```

