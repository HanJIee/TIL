# CSS

[TOC]

---

### #기본용어

---

#### 1. <style>태그

interanl : <style>태그를 이용하여 스타일 시트를 모아놓은 스타일


	<head>
	<style>
		선택자{
			속성:속성값;	
			속성:속성값;
			}
	</style>
	</head>

external :  외부스타일시트, 스타일 시트코드만 있는 파일

```
<head>
<link rel="stylesheet" href="경로" type="text/css"/>
</head>
```



---

#### 2. background

```
background-color: rgb(100,250,120); #ddd; red;
background-image:url(../img/04.jpg);
background-repeat: ▶ 반복 no-repeat, repeat-x, repeat-y
background-position: 70% 20%; 100px 50px; ▶ left, center, rigth, top, meddle, bottom
background-attachment: fixed; ▶ fixde, scroll (이미지 고정)
background-size: 100% 300px; ▶ 배경이미지 크기
```

```
 ▶ 한번에 적용
  body {background: url(../img/01.jpg) no-repeat fixed right center;}
```



---

#### 3. font

```
font-family:"굴림" ▶ 글꼴
font-weight:700; ▶ 굵기
color:red; ▶ 글자색
font-size : px(기본16px), pt, cm, mm ,in(inch) em(현재크기 기준 사이즈 정해짐) 20일때 0.5em -> 10px						
```



----

#### 4. border

```
border-lefe-style, border-right-style, border-top-style, border-bottom-style,
boeder-color : red green blue maroon; ▶ rgb코드, 컬러명
border-width : dotted; border-width: 2px ▶ 선의 두께 (px)
border-style : 선모양(solid:실선 dotted:점선, dashed(긴점선), double:이중선, none, groove:홈, inset:볼록)
```

```
▶ 한번에 적용
border: solid 5px orange;
```



---

#### 5. list

```
list-style-type: none;  (circle, square, upper-alpha...)
list-style-position : outside; inside;
 list-style-image: url("");
```



---

#### 6. attribute (속성 선택자)

```
[속성이름="속성값"]
input[type=text]{color:green;}

$= 특정값으로 끝나는 태그를 선택
img[src$=jpg]{border: 3px solid orange;}

^= 특정값으로 시작하는 태그를 선택
input[value^=등]{background-color: yellow;}

*= 특정값이 포함되어 있는 태그를 선택
input[value*=gu]{background-color: pink;} (태그, 클래스, 속성값 숫자일경우 ''안에)
```



---

#### 7. 결합 선택자

```
▶자손 선택자
div p {스타일;}
```

```
▶자식 선택자
div > p {스타일;}
```



---

#### 8. 동위 선택자

```
▶일반 동위 선택자
div ~ p {스타일;} (<div>태그보다 뒤에 존재하는 <p>태그 모두 선택)
```

```
▶인접 동위 선택자
div + p {스타일;} (<div>태그의 바로 뒤에 존재하는 <p>태그 모두 선택)
```



----

#### 9. 상태 선택자

```
:disabled  비활성화된 컴퍼넌트에 스타일 적용 -> 서버로 데이터도 안넘어감
:enabled 활성화된 컴퍼넌트에 적용하기
:checked  체크된 상태의 input 요소를 선택)
```



---

#### 10. 반응 선택자

```
:focus 커서가 컴퍼넌트에 들어갔을 때(input 활성화)
:hover 마우스 올렸을 때
:link 링크 방문하지 않은 상태
:visited 링크 방문한 상태
:active 링크 클릭 상태
```



---

#### 11. 구조 선택자

```
nth-child(2n) : n번째에 위치하는 자식 -> 246 (2n+1) 135
nth-last-child : 뒤에서 n번째에 위치하는 자식
first-child : 첫번째 객체
last-child : 마지막 객체

nth-of-type : 모든 자식 요소 중에서 n번째로 등장 요소
first-df-type : 모든 자식 요소 중에서 맨 처음으로 등장 요소
last-df-type : 모든 자식 요소 중에서 마지막 으로 등장 요소
```

```
선택 불가되도록 하기
oncontextmenu="return false" : 마우스 오른쪽 버튼 메뉴 제어
onselectstart="return false" : 드래그 시작불가능
```



---

#### 12. 의사 요소

```
::first-letter : 첫번째 글자에 대한 스타일
::first-line : 첫번째 줄에 대한 스타일
::selection : 선택영역에 대한 스타일
```



---

#### 13. shadow

```
text-shadow: -5px -5px 5px red; (왼오 / 위아래 / 투명 / 색상)
box-shadow: 10px 10px 10px #ccc;

gradient
https://www.colorzilla.com/gradient-editor/ 참고
```



---

#### 14. position

```
position: static; (좌표 속성값에 영향 받지 x) 정적
position: relative;left: 30px; (내 HTML 기본 위치를 기준으로 위치를 설정) 상대
position: fixed; top:100px; right:100px; (스크롤 되어도 항상 같은 곳에 위치) 지정
position: absolute; left: 250px; bottom:100px; (조상 요소를 기준으로 위치를 설정 조상요소 x -> HTML기준으로 위치 설정) 절대
```



---

#### 15. display

```
visibility : visible; hidden; ▶ 선택된 개체를 보여주거나 숨길수있다. 숨기더라도 공간 유지
dispaly  : block; none; ▶ 선택된 개체를 보여주거나 숨길수있다. 숨김상태에서 공간 반납
				
```

