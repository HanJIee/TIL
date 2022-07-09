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

