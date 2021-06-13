# HTML & CSS
Key Word : CSS, id, class, 배경(background), span, ul, ol, list-style-type, margin과 padding의 개념, position(fixed, absolute, relative)의 개념, ovrflow : visible 속성, 블록레벨 태그, 인라인레벨 태그, border-radius, display(inline, block,...), 배경 그라데이션, box-sizing(content-box, border-box), float, 
<hr/>

## CSS(Cascading Style Sheet)!   
   
 CSS 는 Cascading Style Sheet의 약자로, 종속형 스타일 시트라고 한다. HTML로 브라우저 화면의 뼈대를 잡았다면 페이지의 시각적 표현을 해주는 기능을 담당한다. CSS를 사용하면 텍스트로 이루어진 정보를 시각화하여 사용자에게 더 효율적으로 정보를 전달할 수 있다. 
<br/>
<hr/>
 ### id와 class   
    
 HTML 에서 id는 오직 한개만 가질 수 있는 고유한 값을 뜻한다. 반대로 class는 반복적으로 사용할 수 있는 값에 주로 넣게된다. 따라서, 고유한 element를 사용할 때에는 id를 적용하고, 반면에 고유하지 않은, 계속 반복되는 element의 경우에는 class를 적용해서 작성하면 된다.   
    
 id는 CSS에서 `#`을 이용해 표기하며, class는 원하는 이름값에 `.`을 붙여 사용하면 된다.   
   
 id와 class에 대한 개념은 앞으로도 계속 나올 것이니 예제가 나올 때마다 개념을 잡으면 좋을 것 같다.   
    
<br/>
<hr/>

 ### class의 사용 <br/>
 **class 사용을 통한 줄간격 설정 예제**
<br/>
```  
    <head>
        <style>
            p {
                font-size: 15px;
                border: 1px solid grey;
                padding: 10px;
            }
            .big-line {line-height: 2;}     /*상대크기2em(글자 위아래로 반나눠서)*/
            .small-line {line-height: 0.7;}	/*글자크기의0.7배 만큼 띄움*/
        </style>
    </head>
    <body>
        <h2>블루베리(Blueberry)</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ut dolores facere est magni aliquam quibusdam illum aspernatur blanditiis fuga omnis. Delectus eveniet reprehenderit dolorum eaque corrupti ipsam architecto nobis explicabo.</p>
        <p class="big-line">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ut dolores facere est magni aliquam quibusdam illum aspernatur blanditiis fuga omnis. Delectus eveniet reprehenderit dolorum eaque corrupti ipsam architecto nobis explicabo.</p>
        <p class="small-line">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ut dolores facere est magni aliquam quibusdam illum aspernatur blanditiis fuga omnis. Delectus eveniet reprehenderit dolorum eaque corrupti ipsam architecto nobis explicabo.</p>
        
    </body>
 ```
    
**class 차이에 따른 줄간격의 예제 이미지.**
<br/>
![image](https://user-images.githubusercontent.com/84966961/121807666-15ead300-cc90-11eb-8da0-67bf232f28f6.png)   
<br/>
 .big-line은 원본 줄간격의 상대 크기 2배로 늘리는 설정이며, .samll-line은 글자 크기의 0.7배로 줄여보이게 한다. 단, 줄 간격은 위아래에 포함되는 간격에 모두 적용되므로 이 점을 잘 기억해 두어야 한다.   

   
 또한 클래스를 적용하고 싶다면 `<p class="big-line">` 다음과 같이 원하는 태그에 `클래스="클래스이름명"` 을 넣어주면 된다.
   
<br/><br/><br/>
<hr/>

### 배경(background) 속성   

<br/>

**배경 예제 코드**   
   

```
<head>
    <meta charset="utf-8">
    <title>backStyle</title>
    <style>
        body {
            background-image: url('images/bg1.png');
            background-repeat: repeat-y;
        }
        div {background-color: rgba(255, 255, 255, 0.712);}
    </style>
</head>
<body>
    <div>
        <h1>초콜릿(chocolate)</h1>
        <p><span style="background-color:red;"> Lorem ipsum dolor sit amet consectetur</span> adipisicing elit. Magni quaerat eaque ullam quod officia rerum nisi
            repudiandae, tempora beatae laborum doloremque quidem blanditiis, ab quos veniam dolores voluptate tempore
            consequuntur!</p>
    </div>
</body>
```
   
   
**예시 화면**   
   
![image](https://user-images.githubusercontent.com/84966961/121808452-87785080-cc93-11eb-8716-0200978b4c64.png)
   
 코드를 보면 div와 body에 각각 배경에 관한 속성을 넣어준 것이 보인다.<br/>
<br/>
 body 를 보면 url을 통해 상대 경로로 image 폴더에 있는 bg1.png 파일을 적용시킨것을 알 수 있다. 또한 background-repeat 라는 속성을 이용하여 y축(위아래)으로만 반복시킨 것을 예제 이미지를 통해 확인이 가능하다.<br/>
<br/>
 그와 달리 div 태그는 하얀색의 rgb값에 alpha 값을 0.7정도로 주어 투명도를 주었다. 실제 예제 이미지를 보면 뒤의 body의 백그라운드 이미지가 하얗게 투과되는 것이 보인다.<br/>
<br/>
 이번 예제에서는 또한 span이라는 새로운 태그를 써서 특정 부분의 텍스트 블럭에만 빨간색의 배경색을 주었다. span 태그는 CSS와 함께 사용되며 div와는 달리 줄바꿈이 되지 않는 태그이다.<br/>

<br/><br/><br/><br/>
<hr/>
 ### Market 예제
 ```
<head>
	<meta charset="utf-8">
	<title>market</title>
	<style>
		#container {  /* 전체 콘텐츠를 감싸는 div */
			width:650px;  /* 너비 */
			margin:0 auto;  /* 가로로 중앙에 배치 */
			padding:5px;	/* 테두리와 내용 사이의 패딩 여백 */		
		}
		#check {   /* 텍스트 부분을 감싸는 div */
			width:640px;  /* 너비 - 그림 너비 값에 맞춤 / 컨테이너보다 작게해서 내용물이 흘러넘치는 것을 방지 */
			border:1px solid #ccc;  /* 테두리 */
			text-align: center
		}		
		h1 {
			background-color: black;
			color: white;
			font-size: 1em;
			margin: 0;
			padding: 10px;
		}
		h2 {
			color: red;
			font-size: 1.2em;
			text-align: center;
		}
		p {
			font-size: 1.5em;
			font-weight: bold;
			line-height: 2em;
			text-align: center;
		}
		.colored {color: blue;}
		.small-font {
			font-size: 0.7em;
			font-family: ;}
		.small {
			font-size: 1.5em;
			text-align: center}
	</style>
</head>
<body>
	<div id="container"><!--id는 두가지 효과 기입 불가능. 그렇기 때문에 class사용-->
		<img src="images/top.jpg" alt="가정용 꿀사과 - 흠집이 있고 약간은 못생겼지만 맛과 영양은 그대로입니다. 질좋은 사과를 저렴하게 즐겨보세요">		
		<div id="check">
			<h1>확인하세요</h1>
			<h2>주문 및 배송</h2>
			<p><span class="colored">오후 2시 이전 </span>주문건은 당일 발송합니다<br>
			2시 이후 주문건은 다음날 발송합니다(주말 제외)</p>
			<hr>
			<h2>교환 및 환불</h2>
			<p>불만족시 <span class="colored">100% 환불</span>해 드립니다<br>
			고객센터로 전화주세요</p>
			<hr>
			<h2>고객센터 </h2>
			<p>0000-0000<br>
			<span class="small-font">상담시간 : 오전 9시 ~ 오후 6시 (토/일, 공휴일 휴무)</span><br>
			<span class="small-font">p 1.5* span 0.7</span></p>
			<span class="small">span 1.5</span>
			<!--스팬속성에는 윤곽에 대한 기준이 없어서 text-align이 안먹음.-->
		</div>
	</div>
  ...
```
   
 **예제 코드 실행 이미지**   
    
 <img src="https://user-images.githubusercontent.com/84966961/121808937-c7d8ce00-cc95-11eb-89d3-033f85117fff.png" width="30">   
   
 CSS의 속성들은 비교적 직관적이기에 코드를 읽어보고 실제로 나오는 이미지와 비교해보면서 CSS를 문법을 익히면 도움이 될 듯하다.   
   



   
<br/><br/><br/>
<hr/>
 ### ul, ol 태그와 list-style-type  
   
 **예제 코드**
```
        <style>
            .book1 {
                list-style-type: lower-roman; /*리스트 머리기호 제어문*/
            }
            .book2 {
                list-style-type: none; /*기호 없앰*/
                
            }
        </style>
    </head>
    <body>
        <ul>
            <li>Do it! 시리즈</li>
            <li>된다 시리즈</li>
            <li>DCM 프로 사진가</li>
            <li>데이터과학 시리즈</li>
        </ul>
        <h1>도서 시리즈</h1>
        <ol class="book1">
            <li>Do it! 시리즈</li>
            <li>된다 시리즈</li>
            <li>DCM 프로 사진가</li>
            <li>데이터과학 시리즈</li>
        </ol>

        <ol class="book2">
            <li>Do it! 시리즈</li>
            <li>된다 시리즈</li>
            <li>DCM 프로 사진가</li>
            <li>데이터과학 시리즈</li>
        </ol>
    </body>
```   
**코드 예제 이미지**   
![image](https://user-images.githubusercontent.com/84966961/121809135-94e30a00-cc96-11eb-8615-c75cee6d2426.png)
   
 첫번째 ul 태그는 unordered list의 약자로 예제 이미지처럼 단순 점표현으로 리스트를 나열한다.    
    
 두번째의 ol 태그는 ordered list의 약자로 원래는 1. 2. 3. 4. 이렇게 숫자로 표현되지만 CSS 속성에서 list-style-type이라는 속성을 통해 로마자 기호로 바꾸어 주었다.   
    
 마지막 세번째의 ol 태그는 list-style-type이라는 속성에 none을 주어 기호 자체를 없애 버렸다.    
    

<br/><br/><br/>
<hr/>   
  ### position 속성을 이용한 이미지 위의 글씨 위치 시키기
   
 **예제 코드**
```
<head>
    <meta charset="utf-8">
    <title>apple</title>
    <style>
        body {
            font-family: "맑은 고딕", 돋움;
        }
        .container{
            position: relative;
            width: 600px;
            height: 400px;
            padding: 20px;
            border: 1px solid white;
            background: url('images/apple.jpg') no-repeat;
            background-size: cover;
        }
        .content {
            position: absolute;
            top: 300px; /*위로부터 위치 값.*/
            width: 90%;
            background: rgba(255, 255, 255, 0.5);
            text-align: center;
            padding: 10px;
        }
        h1 {
            font-size: 30px;
            text-align: center;
        }
    </style>
</head>
<!--박스모델 블록태그 인라인태그 인라인블록태그-->
<body>
    <div class="container">
        <div class="content">
            <h1>하루 한알의 사과는 의사를 멀리 한다</h1>
        </div>
    </div>
</body>
```
**코드 예제 이미지**   
![image](https://user-images.githubusercontent.com/84966961/121809332-5c8ffb80-cc97-11eb-8b13-3de7ad4bc5a6.png)
   
 태그를 보고 이해를 해보면 좋을 듯 싶다.  
     
 이 예제에서 주의깊게 봐야하는 점은 position 속성이며 content 클래스에 `position : absolute;` 로 부모를 기준으로 위치를 고정시킨다는 점이다. 이후 top값을 이용하여 text 태그인 h1 태그의 위치를 이동시켰다. 중앙 정렬은 text 태그의 속성인  `text-align` 속성을 `center`로 주어 처리하였다.


<br/><br/><br/>
<hr/>   
  ### Content의 margin과 padding의 개념   

 웹페이지에서 margin, padding, border의 개념은 중요하다. 다음 이미지를 통해 알아보자.

 ![image](https://user-images.githubusercontent.com/84966961/121809690-bd6c0380-cc98-11eb-8cc5-af99b160ef0a.png)
   
 모든 HTML 요소는 박스 요소로 구성되며, 이것을 **박스 모델(box model)** 이라고 부른다. 가운데에는 content라는 우리가 웹페이지 내부에 넣고 싶은 내용물이 있으며, 이 컨텐츠는 항상 위의 그림처럼 몇가지 테두리에 둘러 쌓여 있다.   
    
1. 내용(content) : 텍스트나 이미지가 들어있는 박스의 실질적인 내용 부분입니다.
2. 패딩(padding) : 내용과 테두리 사이의 간격입니다. 패딩은 눈에 보이지 않습니다.
3. 테두리(border) : 내용와 패딩 주변을 감싸는 테두리입니다.
4. 마진(margin) : 테두리와 이웃하는 요소 사이의 간격입니다. 마진은 눈에 보이지 않습니다.
   
 각 방향 마다 `-top, -right, -bottom, -left`을 붙여 CSS 상에서 설정할 수 있다.   
   
 CSS에서 height와 width 속성을 바꿀 때 영향을 주는 부분은 오로지 내용(content) 부분만을 대상으로 한다는 점 또한 중요합니다. 높이와 너비는 오로지 컨텐츠에만 영향을 주며 패딩, 테두리, 마진의 값과는 다른 값입니다.   
    
 각 속성 값에는 px, dp, %(부모크기에 대한 퍼센티지)가 들어갈 수 있습니다. 만약 반응형 웹을 만들고 싶다면 %가 주로 들어갈 것입니다. 
   
   
<br/><br/><br/>
<hr/>   
  ### position(fixed, absolute,)의 개념, ovrflow : visible 속성   
  
 **예제 코드**
```
<head>
    <meta charset="utf-8">
    <title>box</title>
    <style>
        body {
            background-color: black;
        }
        div {
            background-color: teal;
            width: 200px;
            height: 200px;
            padding: 10px; 
            border: 10px blue solid;
            margin: 100px;/*원래 크기 + (패딩 + 보더 + 마진)*2 이 컨텐츠의 크기*/
            text-align: center;
            vertical-align: center;
            }
        span {background-color: tomato;}
        .info {position: fixed;
        top: -1000 px;
        color: white;
        }
        p {
            color: white;
            overflow: visible;
            
            width: 200px;
            height: 200px;
            padding: 10px; 
        }
    </style>
</head>
<!--박스모델 블록태그 인라인태그 인라인블록태그-->
<body>
    <div>width: 200px;<br>
        height: 200px;<br>
        border: 10px blue solid;<br>
        margin: 100px;
    <p>
    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Eveniet consequatur sint delectus aspernatur voluptas quos obcaecati eum nulla saepe reiciendis debitis quod quam nisi dolor illo, culpa esse excepturi? Enim.        
    </p></div> <!-- 블록레벨 태그 : p,h1,ul,form,hr,table -->
    <!-- 횡으로 끝까지 있는 블록(전체 한 줄에 대한 태그), 블록의 크기를 정해줘야함. width, height 등을 정해줘야함.
    배치상 블록 옆에 블록이 올 수 없음. -->
    <span>23456</span><span>78910</span> <!-- 인라인레벨 태그 : span,img,input,label,button-->
    <!-- 영역이 들어간 만큼만 설정되기 때문에 크기값이 적용되지 않음. -->
    <p class="info">
        margin: 100px;
        width: 200px;
        height: 200px;
        border: 10px blue solid;</p>
        <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
        
</body>
```   
**코드 예제 이미지**   
![image](https://user-images.githubusercontent.com/84966961/121809550-2901a100-cc98-11eb-855d-2ebfb1bd7fbd.png)
   
 예제를 통해 margin, border, padding에 값과 속성을 주는 법을 알 수 있다.   
 
 이외에도 p태그 내부 속성으로 `overflow : visible;` 이라는 속성을 주었는데 이는 말그대로 내용물이 테두리를 넘쳐 흐르더라도 보이게 해준다는 의미이다. overflow는 단순히 이 기능 말고도 다른예제를 통해 다른 기능을 알아볼 예정이다.  
    
 또한, 마지막 p 태그에는 info 클래스가 붙어있는 것을 알 수 있다. `position : fixed;`라는 속성을 주게 되면 웹 브라우저 상에서 절대 위치로 고정되게 되는 속성이다. 이 말은 스크롤로 위치를 변화시켜도 절대 고정이라는 뜻이다. 주로 다양한 홈페이지에서 볼 수 있는 top 버튼이나 로그인 로그아웃 버튼 혹은 header 부분에도 사용된다.

   
<br/><br/><br/>
<hr/>   
  ### 블록레벨 태그와 인라인레벨 태그 개념   
   
 위의 코드를 통해 알 수 있는 내용들이다. 읽어보고 넘어가자.
 
 1. 블록레벨 태그 : p,h1,ul,form,hr,table   
	횡으로 끝까지 있는 블록(전체 한 줄에 대한 태그), 블록의 크기를 정해줘야함. width, height 등을 정해줘야함. 배치상 블록 옆에 블록이 올 수 없음.   
	   
 2. 인라인레벨 태그 : span,img,input,label,button   
	영역이 들어간 만큼만 설정되기 때문에 크기값이 적용되지 않음.   
   
   
<br/><br/><br/>
<hr/>   
  ### 블록의 인라인화와 인라인의 블록화    
 **예제 코드**
```
<head>
    <meta charset="utf-8">
    <title>box2</title>
    <style>
        div {
            margin: 20px;
            border: 1px solid #c00;
            border-radius: 5px;
        }
        #inline p{
            display: inline;
            margin: 10px;
        }
        #block img,button{ /*하위선택자 구성방식
        명령 : block id를 찾아서 img, button 태그에 아래와 같은 효과를 주세요.*/
            display: block; /*block <-> inline 속성 변경*/
            margin: 10px;
        }
        nav a{
            display: inline;
        }
    </style>
</head>

<body>
    <nav><ul><li>
        <a href="#">애완견 종류</a>
        <a href="#">입양하기</a>
        <a href="#">건강돌보기</a>
        <a href="#">더불어살기</a>
    </li></ul></nav>
    <ul><li>
        <a href="#">애완견 종류</a>
        <a href="#">입양하기</a>
        <a href="#">건강돌보기</a>
        <a href="#">더불어살기</a>
    </li></ul>
    <div id="inline">
        <img src="images/doll1.jpg" alt="인형1">
        <p>이것은 인라인이 된 문단</p>
        <img src="images/doll2.jpg" alt="인형2">
        <img src="images/doll3.jpg" alt="인형3">
    </div>
    <div id="block">
        <img src="images/doll1.jpg" alt="인형1">
        <img src="images/doll2.jpg" alt="인형2">
        <img src="images/doll3.jpg" alt="인형3">
        <button>안녕~나는 블록</button>
        <img src="images/doll3.jpg" alt="인형3">
    </div>
</body>
```   
**코드 예제 이미지**   
 ![image](https://user-images.githubusercontent.com/84966961/121810357-83503100-cc9b-11eb-994c-94b661ba8e9c.png)    
   
 이 예제에서 살펴볼 부분은 인라인 태그가 블록 태그처럼 보이게 할 수 있고, 그 반대의 경우도 가능하다는 점이다.   
    
 이 기능을 위한 속성은 display이다. 아래의 이미지를 보면 사진은 인라인 태그이지만 블록 태그인 p 태그는 중간에 낄 수가 없다. 하지만 속성에 `display : inline;`이라는 속성을 주어 p태그를 인라인화 시켰고, 그 결과 아래 이미지처럼 p태그와 이미지 태그가 나란히 줄지어 있는 것을 알 수 있다.   
   
 이 외에도 `border-radius: 5px;`라는 속성을 주어 모서리를 깎은 것을 알 수 있다.
   
![image](https://user-images.githubusercontent.com/84966961/121810483-07a2b400-cc9c-11eb-9468-dd145d35ee17.png)
   
 이와는 반대로 인라인 태그인 버튼 태그를 block 화 시켜 한줄이 건너띄어진 것을 확인할 수 있다.

   
 <br/><br/><br/>
<hr/>   
  ### border-radius 속성을 이용한 원 만들어보기
 **예제 코드**
```
<head>
    <meta charset="utf-8">
    <title>display
    </title>
    <style>
        body div {
            width: 200px;
            height: 200px;
            margin: 30px;
            padding: 20px;
            display: inline-block;
            border: 5px #ff0 solid;/*top right bottom left*/
            /* border-top: 두께 색상 선종류 ;*/
            border-radius: 120px; /*좌상 우상 우하 좌하*/
            /* 반지름 + padding */
            text-align: center;
            line-height: 200px; /*행간이 위아래로 나뉘어짐 위 100 아래 100*/
        }

        .d1 {
            background-color: tomato;
            
            margin: 100px;
        }
        .d2 {
            background-color: teal;
        }
        .d3 {/* Permalink - use to edit and share this gradient: https://colorzilla.com/gradient-editor/#1e5799+0,2989d8+50,207cca+51,7db9e8+100;Blue+Gloss+Default */
background: #1e5799; /* Old browsers */
background: -moz-linear-gradient(top,  #1e5799 0%, #2989d8 50%, #207cca 51%, #7db9e8 100%); /* FF3.6-15 */
background: -webkit-linear-gradient(top,  #1e5799 0%,#2989d8 50%,#207cca 51%,#7db9e8 100%); /* Chrome10-25,Safari5.1-6 */
background: linear-gradient(to bottom,  #1e5799 0%,#2989d8 50%,#207cca 51%,#7db9e8 100%); /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#1e5799', endColorstr='#7db9e8',GradientType=0 ); /* IE6-9 */

            background-color: turquoise;
        }
    </style>
</head>
<body>
    <div class="d1">div1 tomato color</div>
    <div class="d2">div2 teal color</div>
    <div class="d3">div3 turquoise color</div>
</body>
```   
**코드 예제 이미지**   
![image](https://user-images.githubusercontent.com/84966961/121810599-7e3fb180-cc9c-11eb-8992-3aaf15fc7d94.png)   
   
 이 예제는 border-radius 속성을 이용하여 모서리를 깎아 원을 만드는 예제이다.   
      
 이외에도 div3번을 보게 되면 배경에 그라데이션이 들어간 것을 알 수 있는 데 구글에서 검색을 통하여 css코드의 그라데이션을 만들어줄 수 도 있고 혹은 직접 코드를 작성할 수 도 있다.
    
 그라데이션 생성기 웹 페이지 : https://colorzilla.com/gradient-editor/#1e5799+0,2989d8+50,207cca+51,7db9e8+100;Blue+Gloss+Default


   
 <br/><br/><br/>
<hr/>   
  ### box-sizing 속성   
 **예제 코드**
```
	<head>
		<meta charset="utf-8">
		<title>box-sizing</title>
		<style>
            .box1 {
                box-sizing: content-box; /*디폴트값*/
                width: 300px; /* content 까지만 너비가 300*/
                height: 150px;
                margin: 10px;
                padding: 30px;
                border: 1px solid red;
            }
            .box2 {
                box-sizing: border-box; 
                width: 300px; /*border 까지 너비가 300*/
                height: 150px;
                margin: 10px;
                padding: 30px;
                border: 1px solid red;
            }
		</style>
	</head>
	<body>
        <div class="box1">box-sizing = "content-box"</div>
        <div class="box2">box-sizing = "border-box"</div>
	</body>
```   
**코드 예제 이미지**   
![image](https://user-images.githubusercontent.com/84966961/121810827-408f5880-cc9d-11eb-9638-790acbd9143f.png)   
   
 box-sizing 속성은 아주 유용한 속성이다. 간단히 말해서 너비와 높이값을 정할 때 어디를 기준으로 맞출 지를 정하는 것인데 속성값 중 content-box 값이 디폴트 값이다. 즉 컨텐츠의 크기를 너비와 속성으로 정해주는 것이고 나머지 padding, border, margin 값은 컨텐츠 크기에 더 해진다고 보면 된다.
    
 그러나 만약 border-box 값을 사용한다면 padding과 border 값이 자동으로 설정한 높이와 너비에서 빠져나간다. 즉, border-box 시 너비 값은 양 끝의 border 까지의 너비값을 정해주는 것이다.
   
 **이해를 위한 이미지**
![image](https://user-images.githubusercontent.com/84966961/121811040-ff4b7880-cc9d-11eb-8806-35b6481d5d1c.png)
출처 : https://stackoverflow.com/questions/46923610/css-resetting-margin-and-padding

   
 <br/><br/><br/>
<hr/>   
  ### 페이지의 구성을 잡아주는 float    
 **예제 코드**
```
	<head>
		<meta charset="utf-8">
		<title>float</title>
		<style>
            div {
                padding: 20px;
                margin: 10px;
            }
            .box1 {
                background: blueviolet;
                float: left; /*블록화한 것들을 위치시킬때 쓰는 속성*/
            }
            .box2 {
                background: chartreuse;
                float: left;
            }
            .box3 {
                background: firebrick;
            }
            .box4 {
                background: greenyellow;
            }
            /*float으로 인해 뜬 공간을 아래 블록이 와서 메꿔주는 방식.*/
		</style>
	</head>
	<body>
        <div class="box1">박스1</div>
        <div class="box2">박스2</div>
        <div class="box3">박스3</div>
        <div class="box4">박스4</div>
	</body>
```   
**코드 예제 이미지**   
![image](https://user-images.githubusercontent.com/84966961/121811078-23a75500-cc9e-11eb-88b5-c735d01a347a.png)   
   
 float은 영단어 뜻처럼 화면상에서 띄워서(마치 물에 띄우듯) 블록들을 위치시킬 수 있도록 하는 속성이다.   
    
 예시의 사진 처럼 박스 1과 2는 float 처리가 되어있고 left 방향으로 이동한 것을 알 수 있다. 그런데 float 됨과 동시에 화면상에서 떠오르므로 아래에 존재해야할 박스 3이 아래에서 딸려 올라와 박스1과 2에 겹쳐진 것을 볼 수 있다. 이것이 **float**의 기능이다.   
   
 우리는 float을 통해 블록 태그들을 원하는 곳에 위치시킬 수 있다.

   
 <br/><br/><br/>
<hr/>   
  ### 
 **예제 코드**
```

```   
**코드 예제 이미지**   











 <br/><br/><br/>
<hr/>   
  ###  
 **예제 코드**
```

```   
**코드 예제 이미지**   
 <br/><br/><br/>
<hr/>   
  ### 블록레벨 태그와 인라인레벨 태그    
 **예제 코드**
```

```   
**코드 예제 이미지**   
 
 ```
 <input type="text" placeholder="공백없이 입력하세요." name="id">
 <input type="text" value="실제로 들어가는 값" name="id">
 ```
    
  위 두 코드의 차이점은 placeholder와 value 이다. value 값은 실제 텍스트 창에 웹사이트가 로드시 값이 저장된 상태로 출력되고, placeholder는 예시문의 기능으로 회색글씨에 바탕에 보이게 된다.   
**예시 사진**
![image](https://user-images.githubusercontent.com/84966961/121778525-2b012c80-cbd2-11eb-8ab1-5642c812c061.png)
      
#### radio 타입 설명   
```
            <dd><input type="radio" name="hobby" id="" checked> 웹퍼블리싱</dd>
            <dd><input type="radio" name="hobby" id=""> 웹 애플리케이션 개발</dd>
            <dd><input type="radio" name="hobby" id=""> 개발 환경 개선 </dd>
```
   
 radio 타입은 반드시 name 값과 value 값이 있어야 하며 동일한 name 값을 이용해 복수 선택 불가능인 한 그룹으로 묶어주는 기능을 한다. checked 라는 속성은 웹브라우저 출력시 라디오 버튼이 디폴트로 체크되어있을지 선택하는 속성이다.   
   
#### submit과 reset 타입 설명
```
<input type="submit" value="접수하기" name="" id="">
<input type="reset" value="다시 쓰기" name="" id=""><br>
```
   
 form 태그로 묶인 내용들을 summit 태그를 통해 form 태그 action 속성에 지정해준 파일로 데이터를 전송한다.
 reset 태그는 말그대로 초기화, 새로고침 기능과 비슷한 기능이다.

#### 일반 button 타입 설명   
   
```
<input type="button" value="경고메세지" onclick="alert('메세지출력')" name="" id="">
```
 버튼 타입에는 onclick 속성을 넣어 참고사항 등 경고 표시를 할 수 있으며 다양한 기능을 수행할 수 있다.
   
### textarea 태그 
```
<textarea name="" id="" cols="60" rows="7" placeholder="본사 지원 동기를 간략히 써 주세요."></textarea>
```
   
 textarea 태그는 일정한 크기를 가진 텍스트 창을 구현해주는 태그이다. 다음과 같은 모습으로 텍스트 창이 구현된다.   
    
![image](https://user-images.githubusercontent.com/84966961/121778846-cd6ddf80-cbd3-11eb-8c0d-f82fd32f20a1.png)

### checkbox 태그
```
		<label for="">수강과목 <br>
			<input type="checkbox" name="" id=""> java <br>
			<input type="checkbox" name="" id=""checked> css <br>
			<input type="checkbox" name="" id=""> sql <br>
		</label>
```

 말그대로 체크박스 기능. 복수 선택이 가능하다. checkbox도 checked를 통해 브라우저 출력시 디폴트로 체크되어있을 박스를 지정할 수 있다.    
   
![image](https://user-images.githubusercontent.com/84966961/121779018-9815c180-cbd4-11eb-9b76-4d40d4113787.png)
   
### select 태그
```
		<select name="" id="">
			<option value="1">직업선택</option>
			<option value="2">개발자</option>
			<option value="3">의사</option>
			<option value="4">기사</option>
		</select><br>
```
![image](https://user-images.githubusercontent.com/84966961/121779044-b7145380-cbd4-11eb-8697-3323bff02366.png)
   
select 태그는 위의 사진처럼 선택창을 만들어주는 태그이다.

### 시간과 날짜 관련한 태그
```
		시간 </label><input type="time" name="" id="">
		날짜출력 </label><input type="date" name="" id="">
		시간 </label><input type="datetime" name="" id="">
		로컬시간 </label><input type="datetime-local" name="" id="">
```   
   
  time 태그는 시간을 선택할 수 있다.
  date 태그는 날짜를 선택할 수 있다.
 시간박스를 만들어주는 태그이다.
 로컬 시간 태그는 연도와 달력을 볼 수 있다.
   
![image](https://user-images.githubusercontent.com/84966961/121779206-841e8f80-cbd5-11eb-9be7-9f6e89cddd51.png)
   
### color 태그 
```
		색상선택 </label><input type="color" name="" id="">
```
![image](https://user-images.githubusercontent.com/84966961/121779218-a4e6e500-cbd5-11eb-916c-5f47ed84cc2a.png)
   
 RGB 색상을 선택할 수 있다.

### image 태그
```
		<input type="image" src="images/orange.jpg" width="300" name="" id="">
```
   
 이미지를 넣을 수 있다.

<hr/>
   
  ## Hello CSS
    
```
<style> 
    /*선택자 {속성:값;} 로 효과를 주는 방식은 전체적으로 바꿀때 용이.*/
        p {
            color: rgba(12, 8, 247, 0.514); /*R,G,B,Alpha투명도*/
            font-family: 'Ubuntu', sans-serif; /*영어*/
            font-family: 궁서, 돋움, "맑은 고딕"; /*한글*/ 
            font-family: 'Nanum Pen Script', cursive; /*한글2 : 나중에 선언되는 코드가 최종적으로 적용됨. 영어 우분투도 사라짐.*/
            font-size: 0.05em;
            font-weight: bold;
            text-decoration: underline;
            text-transform: capitalize;}
        /*  font-family : 글꼴 1,2,"스페이스가 들어가면 쌍따옴표" 우선 적용(1번이 지원안될시 2번....)
            font-size : 절대 크기(px,pt), 상대 크기(em,%)
            font-weight: 굵게
            text-decoration : 텍스트에 각종 선에 대한 옵션(underline:밑줄,line-through:취소선,none:선 없앰.
            text-transform : 대소문자 변경 옵션)
        */
        h1{text-shadow: 3px -3px 5px red, 2px -3px 4px orange, 1px -1px 3px yellow ;/*속성값 : 가로 세로 번짐 색상*/}
        </style>
		
    <!--스타일 주는 법
        1. head style 칸에 입력
        2. 태그에 곧장 입력하는법 <body style:~~~~; >
        3. 파일을 만들어서 불러오는 방식
        - 특정 양식을 정해놓아서 다른 파일도 가져다 쓸 수 있도록 효율을 높인 방식.-->

        <!-- <link rel="stylesheet" type="text/css" href="mystyle.css"> -->
        <!--mystyle.css 의 스타일 값을 적용시킴 link 시킴.-->
```

 **CSS 연습 예제**
```
<body>
    <h1>HTML5</h1>
    <p style="color: red;">오늘도 즐거운 하루 되세요.</p>
    <p style="color: orange;"><b>오늘도 즐거운 하루 되세요.</b> </p>
    <p style="color: yellow;">오늘도 즐거운 하루 되세요.</p>
    <p style="color: green;">오늘도 즐거운 하루 되세요.</p>
    <p style="color: blue;">오늘도 즐거운 하루 되세요.</p>
    <p style="color: navy;">오늘도 즐거운 하루 되세요.</p>
    <p style="color: purple;">오늘도 즐거운 하루 되세요.</p>
    <p>
        이 것은 디폴트 색 <br>
        <i>this is ubuntu italic</i>
        이 것은 나눔 펜 스크립트
    </p>
    <link rel="stylesheet" href="submit.html" style="text-decoration: none;">네이버
    <!-- 앞으로는 바뀌지 않을 경우 바로 지정하는 게 좋음.-->
</body>   
```

**예제 이미지**   
![image](https://user-images.githubusercontent.com/84966961/121779360-33f3fd00-cbd6-11eb-9568-43f38a5bd3b4.png)

<hr/>
   
 ## Class와 id의 개념
    
  **예제 태그**
```
<html>
<head>
    <title>text-shadow</title>
    <meta charset="utf-8">
    <style>
        
        body{
            background: white; /*문서배경색*/
        }
        h1{
            font-size: 80px;
            font-family: "Arial Rounded MT";
            letter-spacing: 4px; /* 자간 */
        }
        .shadow3 { 
            color: black;
            text-shadow: 0px 0px 4px white,0px -5px 4px yellow ,2px -10px 6px orange ,-2px -15px 11px rgba(255, 145, 0, 0.829), 4px -20px 18px red ;}
        } 불모양 만들기
        p {letter-spacing: 0.2em;} /* 자간 조절 */
        div {
            width: 150px;
            height: 150px;
            border: 1px solid black;
            white-space: pre-wrap;} 
            /* nowrap 테두리로 씌우지않음
                pre 내용 그대로
                pro-wrap 내용 그대로 씌워서 */
        .c1 {color: red;}
        .c2 {color: green;}
        .c3 {color: blue}
        .c4 {font-size: 30px;}

        #p1 {font-size: 10px;}
        #p2 {font-size: 20px;}
        #p3 {font-size: 30px;}
        #p4 {color: purple;}

        h1,h2 {text-align: center;} /* 그룹선택자 , : 두가지를 동시에 선언 가능 */
        .h2 {text-align: left;}
    </style>
</head> 
<body>
    <h1 class="shadow3 h2">HTML5</h1> 
    <!-- h2라는 클래스 선언 가능, 초기 선언에 덮어쓰면(h1은 center가 디폴트지만 h2 클래스로 덮음) 최종 선언이 잔류함.-->
    <h1>안녕하세요</h1>
    <h2>안녕하세요</h2>
    <div>안녕하세요               안녕하세요             안녕하세요             안녕하세요        안녕하세요           안녕하세요 </div>
    <p>letter-spacing 자간조절</p>
    <p class="c1 c4">이 것은 c1 클래스(색깔)와 c4 클래스(30px)의 p태그</p>
    <p class="c2">이 것은 c2 클래스의 p태그</p>
    <p class="c3">이 것은 c3 클래스의 p태그</p>
    <div class="c2"> 이것은 클래스 c2의 div</div>
    <!-- 클래스는 태그를 막론하고 다 기능을 함. 따라서 단순 CSS요소를 먹이고싶을때 할 수 있음.-->

    <p id="p1 p4">이 것은 p1 id와 p4 id의 p태그</p>
    <p id="p2">이 것은 p2 id의 p태그</p>
    <p id="p3">이 것은 p3 id의 p태그</p>
    <div class="c2" id="p3"> 이것은 클래스 c2, p3 id의 div</div>
    <!-- class id 혼용 가능.-->

    <p class="c1 c4">이 것은 c1 클래스(색깔)와 c4 클래스(30px)의 p태그</p>
    <p id="p1 p4">이 것은 p1 id와 p4 id의 p태그</p> <!--동시 작용 불가능-->
    <!-- class id의 차이점 : 다른 효과 동시 적용 가능 불가능 차이-->

</body>   
</html>
```

![image](https://user-images.githubusercontent.com/84966961/121779413-7584a800-cbd6-11eb-9715-031ab742e057.png)

 클래스와 id에 대한 예제였다.













