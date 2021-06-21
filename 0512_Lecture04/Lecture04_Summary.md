# HTML & CSS   
Key Word : position(fixed, relative, absolute), Table border 없앰(border-collapse: collapse), Semantic(시맨틱) 태그, 초기화 코드, a:hover, nth-child, last-child, radio 타입을 안보이게 하기, ~, white-space, >, overflow
   
<hr/>
   
## position : fixed   

**0512_1_position_fixed.html**   
```html
<!DOCTYPE html>
<html lang="ko">

<head>
    <meta charset="utf-8">
    <title>position_fixed
    </title>
    <style>
        /*static, relative, absolute, fixed*/
        /*  static  : 디폴트값
            absloute : 브라우저 기준 왼쪽 상단 기준으로 이동
            relative : 현재 코딩 위치를 기준으로 이동
            fixed   : 화면을 기준으로 고정됨. (로그인 버튼, top위로 버튼, navigator 등등) */
        #fx {
            position: fixed;
            top: 5px;
            right: 5px;
            width: 50px;
            height: 50px;
            background: purple;
        }

        #content {
            width: 400px;
        }

        p {
            line-height: 30px;
        }
    </style>
</head>

<body>
    <div id="fx"></div>
    <div id="content">
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia nesciunt voluptates, inventore voluptatum ad
            officiis amet earum excepturi omnis ipsum qui in suscipit, recusandae odit optio saepe blanditiis magnam
            numquam.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia nesciunt voluptates, inventore voluptatum ad
            officiis amet earum excepturi omnis ipsum qui in suscipit, recusandae odit optio saepe blanditiis magnam
            numquam.</p>
    </div>
    <div class="box" id="crd2"></div>
    <div class="box" id="crd3"></div>
    <div class="box" id="crd4"></div>
    <div class="box" id="crd5"></div>
</body>

</html>
```
   
**브라우저 화면**    
![image](https://user-images.githubusercontent.com/84966961/122773010-e7e63e00-d2e2-11eb-8684-df4a67cf1a67.png)   
   
 결과 화면을 보면 `fx` id 값을 준 div 태그가 오른쪽 상단 기준으로 5px 위치에 고정된 것을 알 수 있다. 일전 수업에서도 다루었듯 `fixed` 속성을 주게 되면 스크롤을 내려도 브라우저 상에서 고정된다.   
    
<br/><br/>
<hr/>

## position : relative와 absolute의 활용   
   
**0512_2_position_z-index.html**   
```html
<!DOCTYPE html>
<html lang="ko">
    <head>
        <meta charset="utf-8">
        <title>position_z-index
        </title>
        <style>
            div#wrapper { /*div-> 한정선택자 div 중 wrapper*/
                position: relative;
                width: 150px;
                height: 150px;
                border: 1px solid black;
            }
            .box {
                position: absolute;
                width : 50px;
                height : 50px;
            }

            #b1 {
                top: 0;
                left: 0;
                z-index: 15; /*앞뒤 위치 변환*/
                background : red;
            }
            #b2 {
                top: 15px;
                left: 30px;
                z-index: 10;
                background : yellow;
            }
            #b3 {
                top: 30px;
                left: 15px;
                background : blue;
            }
            

        </style>
    </head>
    <body>
        <div id="wrapper">
            <div id="b1" class="box">1</div>
            <div id="b2" class="box">2</div>
            <div id="b3" class="box">3</div>
        </div>
    </body>
</html>
```

**브라우저 화면**    
![image](https://user-images.githubusercontent.com/84966961/122773843-a5713100-d2e3-11eb-9ee5-2371b32084fd.png)    
   
 한정 선택자를 활용하여 `div#wrapper` divs 중 wrapper인 id값에 `position : relative;`를 주어 기준값을 정해주고,(만약 주지 않는다면 박스들의 기준이 모 wrapper의 기준이 되므로 아마도 웹브라우저 좌상단이 기준이 될 것이다. 그것을 막기 위해 wrapper에 relative를 주어 기준을 잡아주는 것이다.) box 클래스에 `position: absolute;`를 주어 박스들이 wrapper 좌상단 기준으로 절대 좌표를 참조하여 이동한 것을 확인할 수 있다.   

<br/><br/>
<hr/>

## Table border 없애기!   
   
**0512_2_table_border.html**
```html
<!DOCTYPE html>
<html lang="ko">

<head>
    <meta charset="utf-8">
    <title>table_border
    </title>
    <style>
        table {
            width: 300px;
            border-collapse: collapse;
            padding: 10px;
        }
        .table1 {border: 1px solid black;}
        .table1 td{border: 1px dotted black;}
        table tr{width: 5000px;}

    </style>
</head>

<body>
    <table class="table1">
        <caption>프로축구 경기 일정</caption>
        <tr>
            <td>울산</td>
            <td>울산 vs 인천</td>
        </tr>
        <tr>
            <td>부산</td>
            <td>부산 vs 대전</td>
        </tr>
        <tr>
            <td>서울</td>
            <td>서울 vs 강원</td>
        </tr>
    </table>
</body>

</html>
```
    
**브라우저 화면**    
![image](https://user-images.githubusercontent.com/84966961/122774698-62638d80-d2e4-11eb-91d4-417fb7a9f3af.png)

 `border-collapse: collapse;`라는 속성은 테이블의 border 부분이 2줄로 겹쳐 보이는 것을 해소시켜주는 속성이다. Caption 태그를 달아 제목을 달아주고 tr 태그의 너비를 `5000px`로 주어 넓혀 주었다. td 태그에는 `dotted`라는 속성을 활용하여 내부 border는 점선으로 처리한 것을 볼 수 있다.   



<br/><br/>
<hr/>

## Table quiz   
   
 주어진 html 파일을 다음과 같은 상태로 css를 수정하는 것이 퀴즈의 목적이다.   
     
**0512_3_quiz-2.html**
```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>표 스타일</title>
</head>
<body>
  <table border="1">
    <caption>2015 국민 독서실태</caption>
    <thead>
      <tr>
        <th>구분</th>
        <th>성인</th>
        <th>학생</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th>독서율</th>
        <td>65.3%</td>
        <td>94.9%</td>
      </tr>
      <tr>
        <th>연평균 독서량</th>
        <td>9.1권</td>
        <td>29.8권</td>
      </tr>
      <tr>
        <th>공공도서관 이용률</th>
        <td>28.2%</td>
        <td>64.9%</td>
      </tr>      
    </tbody>
  </table>
</body>
</html>
```

    
**기존 테이블 전 -> 후**       
   
<img src="https://user-images.githubusercontent.com/84966961/122775391-0baa8380-d2e5-11eb-90fa-4054f3edd1fb.png" width="40%"> <img src="https://user-images.githubusercontent.com/84966961/122775529-30066000-d2e5-11eb-8a86-c44a85481eb9.png" width="40%">
   
   
**0512_3_quiz-2_ans.html**
```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>표 스타일</title>
    <style>
        table {
            border-collapse: collapse;
            margin: 5px;
            height: auto;
            caption-side: bottom;
            border : 1px solid black;
        }
        table th,td{
            padding: 10px;
            border : 1px solid black;
        }
        table th{
            background: rgba(128, 128, 128, 0.384);
        }
        table td{
            text-align: center;
        }
        .red {background: red;}
    </style>
</head>
<body>
  <table>
    <caption>2015 국민 독서실태</caption>
    <thead>
        <col> 
        <col class="red">
        <col>
      <tr>
        <th>구분</th>
        <th>성인</th>
        <th>학생</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th>독서율</th>
        <td>65.3%</td>
        <td>94.9%</td>
      </tr>
      <tr>
        <th>연평균 독서량</th>
        <td>9.1권</td>
        <td>29.8권</td>
      </tr>
      <tr>
        <th>공공도서관 이용률</th>
        <td>28.2%</td>
        <td>64.9%</td>
      </tr>      
    </tbody>
  </table>
</body>
</html>
```
   
세로로 빨간 바탕을 만드는 법은 직접 칸마다 주는 방법도 있겠지만 위의 코드처럼 하는 것이 가장 쉬운 방법일 것이다. 먼저 `<thead>` 태그를 만들어 table의 head 부분을 정의한다. 이후 내부에 column을 뜻하는 `<col>` 태그를 넣어 칼럼의 갯수 만큼 만들어주고, CSS의 변경을 원하는 열 부분에 속성을 넣어주면 디자인이 바뀌는 것을 확인할 수 있다. 또한 Table의 제목인 `<caption>`태그를 위한 속성으로 CSS table 태그 내부에 `caption-side: bottom;`이라는 속성값을 명명하면 제목이 아랫 부분에 위치하는 것을 알 수 있다.   








<br/><br/>
<hr/>

## HTML에서 의미의 기능을 가지고 있는 Semantic(시맨틱) 태그!   
   
**0512_4_semanticTag.html**
```html
<!DOCTYPE html>
<html lang="ko">

<head>
    <meta charset="utf-8">
    <title>시맨틱태그</title>
    <style>
    </style>
</head>

<body>
    <div id="container"> <!--기능이 아니라 의미(semantic)적으로 쓰는 태그-->
        <header>
            <p>header영역</p>
            <nav>nav영역</nav>
        </header>
        <div id="contents">
            <section>
                <article>section영역1</article>
            </section>
            <section>
                <article>section영역2</article>
            </section>
        </div>
        <aside>aside영역</aside>
        <footer>
            <address>address영역</address>
        </footer>
    </div>
    <article>section영역2</article>
</body>

</html>
```
       
 시맨틱 태그는 의미적으로 사용되는 태그이며 주로 사용 되는 종류를 위의 코드에서 볼 수 있다.    


<br/><br/>
<hr/>

## 실제 홈페이지 화면을 구성해 보기    
       
 다음 브라우저 화면을 보고 실제 홈페이지 화면처럼 구성해보는 실습을 해보자.
       
**브라우저 화면**  
   
![image](https://user-images.githubusercontent.com/84966961/122776968-8c1db400-d2e6-11eb-9d79-346d8a48a171.png)
   
**0512_5_layout2.html**
```html
<!DOCTYPE html>
<html lang="ko">

<head>
    <meta charset="utf-8">
    <title>애완견 돌보기</title>
    <link rel="stylesheet" href="css/layout.css">
    <style>

    </style>
</head>

<body>
    <header>
        <nav>
            <ul>
                <li><a href="#">애완견 종류</a></li>
                <li><a href="#">입양하기</a></li>
                <li><a href="#">건강돌보기</a></li>
                <li><a href="#">더불어살기</a></li>
            </ul>
        </nav>
    </header>
    <article>
        <h2>애완견 종류</h2>
        <div>
            <section>
                <h3> 활달한 강아지</h3>
                <dl>
                    <dt>요크셔 테리어 </dt>
                    <dd>생기있고 활달한 성질을 가지고 있으며 자신보다 몸집이 큰 개나 집에 들어온 침입자를 겁내는 일이 없어 좋은 번견이고 우리나라 최고의의 가정견으로 자리 잡고 있다.</dd>
                    <dt>말티즈 </dt>
                    <dd>애정이 많고, 충실하며 활발한 성격을 소유하고있다. 이 종은 1급 가정견으로 요크셔테리어와 함께 우리나라 최고의 가정견으로 자리잡고 있다.</dd>
                    <dt>포메 라이언</dt>
                    <dd>활기차고 명랑한 개로 유명하고, 걷는 모습이 우아하다.충실하고 우호적인 성격이 가장 먼저 거론된다. </dd>
                    <dt>골든 리트리버</dt>
                    <dd>이 견종은 충성심이 강하고 성격이 활달하여 어린아이나 여성이 상대하기에 적합한 견종이다.참을성 또한 강하여 현재는실내에서도 많이 길러지고 있다.</dd>
                </dl>
            </section>
            <section>
                <h3> 온순한강아지</h3>
                <dl>
                    <dt>쉬즈</dt>
                    <dd>얼굴에서 풍기는 모습처럼 온순, 쉽게 친숙해지고 우호적이며,어린아이나 여성들이 기르기에 적합한 견종이다.</dd>
                    <dt>퍼그</dt>
                    <dd>매우 사려가 깊고 사랑스러운 견종이며 그다지 손질이 필요하지 않고 식사량에 비해 많은 운동량이 필요하지 않다.</dd>
                    <dt>래브라도 리트리버</dt>
                    <dd>침착하고 영리하여 어린이들을 안심하고 맡길 수 있다. 사람을 즐겁게 해주려는 성질이 있다 공을 가지고 노는 것을 가장 좋아한다. 현재 맹인 안내견과 마약견으로 사용중이다.
                        온순한 강아지를 좋아하는 분에게는 적합한 견종이다.</dd>
                </dl>
            </section>
            <section>
                <h3> 사납지만 복종적인 강아지</h3>
                <dl>
                    <dt>미니어쳐핀셔</dt>
                    <dd>경계심이 강하고 영리하며 작은 몸집에 비해 매우 용감하다. 주인에게 매우 복종적이며 작은 몸집에 보디가드 역할을 충실히 수행한다.</dd>
                    <dt>푸들 </dt>
                    <dd>사납진 않으나, 상당히 복종적이며, 지능지수가 애완견종 중 가장 뛰어나다.</dd>
                    <dt>폭스테리어</dt>
                    <dd>가정에서 키우기에 적합한 품종이다. 보호본능이 강하고 정이 많다. 하지만 사냥을 하던 본능이 조금은 남아있어 사나운 면이 있다. 이종을 좋은 품종으로 기르기 위해서는 어릴
                        때부터 엄한 훈련이 필요하기도 하다.</dd>
                </dl>
            </section>
        </div>
    </article>
    <aside>
        <h3>건강한 강아지는</h3>
        <ul>
            <li>코가 젖어있고 눈꼽이 없어야 합니다.</li>
            <li>털에 윤기가 있는 것을 골라야 합니다.</li>
            <li>입에서 고약한 냄새가 나면 병이 있다는 증거입니다.</li>
            <li>가장 활발하게 움직이는 녀석을 고르는게 좋습니다.</li>
            <li>강아지들 중에서 적당한 체구를 유지한 강아지가 좋습니다.</li>
        </ul>
    </aside>
    <footer>
        <p>Copyright 2012 funnycom</p>
    </footer>
</body>

</html>
```
   
**css/layout.css**   
```css
body {
    font-family: "맑은 고딕", "고딕", "굴림";
}

header {
    width: 80%;
    margin: 0 auto;
    background: #069;
    padding: 10px;
    overflow: hidden;
    /* overflow: hidden의 뜻
    내부에 "존재" 하는 모든 컨텐츠의 크기 만큼은 보여주고 나머지는 없앰.
    심지어 float되어 크기가 없는 것 처럼 보이더라도 그 존재 자체의 크기를
    인식하고 남겨서 보여줌.
    ---------
    overflow 자체는 넘어가는 것의 내용을 처리하는 속성이지만
    부모인 header에는 내부 컨텐츠의 속성값을 남기는 기능도 가지고 있음.
    따라서 남은 속성 값을 기준으로 다른 형제 컨텐츠들이 배치됨.*/

}

header nav {
    width: 60%;
    float: right;
    margin: 5px;
}

header ul {
    list-style-type: none;
}

header li {
    display: inline;
}

nav ul li a {
    color: white;
    text-decoration: none;
}
/* 
p{ 
    font-size: 2em;
    line-height: 20px;
} */
article {
    width: 80%;
    margin: 0 auto;
    border: 5px black solid;
    padding: 5px;
}
/* 해결방법찾기 ........  
 기존의 방법으로는 힘든것 같아서, section 3개를 다시 div에 넣어서
 ariticle 내부를 h2와 div 나눠준 후 
 div는 모 그룹으로서 디스플레이 flex를 먹여서 해결함.

*/
div{ 
    overflow: hidden;
    display: flex;
}
article section {
    width: 33%;
    height: 650px;
    border: 1px black dashed;
    float: left;
    margin: 5px;
    padding: 5px;
}

section h3{
    background-image: url('../images/bg-note.png') ;
    background-position: left center;
    background-repeat: no-repeat;
    padding-left: 30px;
}

aside {
    width: 80%;
    margin: 0 auto;
    padding: 10px;
    background: rgb(154, 203, 51);
    height: auto;
    overflow: hidden;
}

footer {
    width: 80%;
    margin: 0 auto;
    color: white;
    background: rgb(51, 52, 51);
    padding: 10px;
    text-align: center;
}
```

 지금까지 배운 내용을 통해 float, overflow, padding, margin 등의 개념 등을 잘 생각하면서 만들어보면 좋을 듯 싶다.   
   
 CSS는 기존과는 달리 `<link rel="stylesheet" href="css/layout.css">` 링크 태그를 통해 불러와 처리하였다.   
   

<br/><br/>
<hr/>

## 다른 홈페이지를 구성하며 기능 더 알아보기    
       
 다음 화면을 구성해보자. 주요 개념으로는 `초기화 코드`, `a:hover`, `nth-child`, `last-child`, `radio 타입을 안보이게 하기`, `~`, `white-space`, `>`, `overflow` 등이 있다. 잘 생각해보자.
       
**브라우저 화면**     
   
![image](https://user-images.githubusercontent.com/84966961/122778027-92f8f680-d2e7-11eb-9da7-d5db1d64df72.png)

   
**0512_7_HTMLPage.html**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Chapter_5</title>
    <link rel="stylesheet" href="css/0512_7_layout.css">
    <link rel="preconnect" href="https://fonts.gstatic.com">
<link href="https://fonts.googleapis.com/css2?family=Itim&display=swap" rel="stylesheet">
    <style>
        /*초기화코드*/
        /*브라우저 자체 padding이 8px을 가지고 있는 것처럼 기본 디폴트값을 
        모두 리셋(보통 0 none)시켜놓고 시작하는 것.*/
        * {
            margin: 0;
            padding: 0;
        }
        body {
            font-family: 'Times New Roman', Times, serif;
        }
        li {list-style-type: none;}
        a {text-decoration: none;}
        img {border: 0;}
        
        /*헤더*/
        #main_header{
            width: 960px;
            margin: 0 auto;
            height: 160px;
            position: relative;
            overflow: hidden;
        }
        #main_header > #title{/* '>' 첫번째 자손중에 라는 뜻 2대 3대 넘어에 있는 title 못잡음.*/
        position: absolute;
        left: 20px;
        top : 30px;
        font-family: 'Itim', cursive;
        }
        #main_header > #main_gnb{ /*main_gnb 위치 설정*/
            position: absolute;
            right: 0px;
            top: 0px;
        }
        #main_header > #main_lnb{ /*main_gnb 위치 설정*/
            position: absolute;
            right: 0px;
            bottom: 10px;
        }
        header nav ul { /*블록들 inline화*/
            display: inline;
        }
        /*gnb메뉴*/
        #main_gnb > ul {
            overflow: hidden;
        }
        #main_gnb > ul > li{
            float: left;
        }
        #main_gnb > ul > li > a{/*디자인 구성*/
            display: block;
            border: 1px black solid;
            padding: 2px 10px;
        } /* 지정하는 곳이 같아도 용도가 다르면 분리*/
        #main_gnb > ul > li > a:hover { /*기능 구성*/
            background-color: black;
            color: #fff;
        } 
        #main_gnb > ul > li:nth-child(1) > a{
            border-radius: 10px 0px 0px 10px;
        }#main_gnb > ul > li:last-child > a{
            border-radius: 0px 10px 10px 0px;
        }
         /*lnb메뉴*/
         #main_lnb > ul {
            overflow: hidden;
        }
        #main_lnb > ul > li{
            float: left;
        }
        #main_lnb > ul > li > a { /*디자인 구성*/
            display: block;
            border: 1px solid black;
            padding: 5px 20px;
        } /* 지정하는 곳이 같아도 용도가 다르면 분리*/
        #main_lnb > ul > li > a:hover { /*기능 구성*/
            background-color: black;
            color: #fff;
        } 
        #main_lnb > ul > li:nth-child(1) > a{
            border-radius: 10px 0px 0px 10px;
        }#main_lnb > ul > li:last-child > a{
            border-radius: 0px 10px 10px 0px;
        }

        /*contents*/
        #content {
            width: 960px;
            margin: 0 auto;
            height: auto;
            position: relative;
            overflow: hidden;
            display: flex;
            justify-content: space-between
        }
        /*main_section*/
        #content > #main_section {
            width: 750px;
        }
        #main_section > article.main_article{
            border: 1px black solid;
            padding: 20px;
            margin-bottom: 10px;
        }
        /*main_aside*/
        #content > #main_aside {
            width: 200px;
            float: right;
        }
        /* --------------------------- */
        /* radio 타입을 안보이게 함. */
        input:nth-of-type(1) {
            display: none;
        }
        input:nth-of-type(2) {
            display: none;
        }
        /* --------------------------- */

        /* 먼저 div 내용을 모두 안보이게 함 */
        input:nth-of-type(1) ~ div:nth-of-type(1)
        /* ~ 같은 형제들(아래)중에 첫번째 div를 안보이게 해라
        */
        {
            display: none;
        }
        input:nth-of-type(2) ~ div:nth-of-type(2)
        /* ~ 같은 형제들(아래)중에 첫번째 div 선택
        */
        {
            display: none;
        }
        /* --------------------------- */

        /* checked 조건을 걸어서 원하는 정보를 보이게 만듬. */
        input:nth-of-type(1):checked ~ div:nth-of-type(1) 
        /* 첫번째 input이 checked상태 라면(:) 형제들중 (~) 첫번째 div를 보여라(block) */ {
            display: block;
        }
        input:nth-of-type(2):checked ~ div:nth-of-type(2) 
        /* 첫번째 input이 checked상태 라면(:) 형제들중 (~) 첫번째 div를 보여라(block) */ {
            display: block;
        }
        /* --------------------------- */

        aside#main_aside > section.buttons {
            overflow: hidden;
        }
        aside#main_aside > section.buttons > label {
            display: block;
            float: left;
            width: 100px;
            height: 30px;
            text-align: center;
            line-height: 28px;
            border: 1px black solid;
            background: black;
            color: white;
            box-sizing: border-box;
        }
        aside#main_aside > section.buttons > label:hover {
            background-color: white;
            color: #000;
        }
        aside#main_aside > input:nth-of-type(1):checked ~ section.buttons > label:nth-of-type(1) {
            background-color: white;
            color: #000;
        }
        aside#main_aside > input:nth-of-type(2):checked ~ section.buttons > label:nth-of-type(2) {
            background-color: white;
            color: #000;
        }
        /*----메뉴탭 끝----*/
        /*----aside 본문 스타일 시작----*/
        aside#main_aside > div.tab_item > ul > li.item {
            overflow: hidden;
            border: 1px black solid;
            border-top: none;
            padding: 10px;
            width: auto;
            height: 45px;
            position: relative;
            display: hidden;
        }

        aside#main_aside > div.tab_item > ul > li.item > a > div.thumbnail {
            float: left;
            display: inline;
            padding-right: 10px;
        }
        aside#main_aside > div.tab_item > ul > li.item > a > div.description {
            float: right;
        }
        aside#main_aside > div.tab_item > ul > li.item > a > div.description strong {
            display: block;
            width: 123px;
            white-space: nowrap;
            /*white-space : 스페이스와 탭, 줄바꿈, 자동줄바꿈을 어떻게 처리할지 정하는 속성*/
            overflow: hidden;
            /*overflow: hidden; - 부모보다 큰걸 안보이게 없앰.
             오버플로우만 쓰면 실제로 한줄로 넘어가는 것이 아님.
             따라서 white-space nowrap으로 강제로 한줄로 쭉 나오게끔 해줘야 ellipsis가 먹힘.*/
            text-overflow: ellipsis;
        }
        
        /*footer*/
        footer#main_footer {
            width: 960px;
            margin: 0 auto;
            margin-bottom: 10px;
            padding: 10px;
            height: auto;
            border: 1px black solid;
            text-align: center;
            box-sizing: border-box;
        }
    </style>
</head>
<body>
    <header id="main_header">
        <hgroup id="title">
            <h1>Rint Development</h1>
            <h2>HTML5 + CSS3 Basic</h2>
        </hgroup>
        <nav id="main_gnb">
            <ul>
                <li><a href="#">Web</a></li>
                <li><a href="#">Mobile</a></li>
                <li><a href="#">Game</a></li>
                <li><a href="#">Simulation</a></li>
                <li><a href="#">Data</a></li>
            </ul>
        </nav>
        <nav id="main_lnb">
            <ul>
                <li><a href="#">HTML5</a></li>
                <li><a href="#">CSS3</a></li>
                <li><a href="#">JavaScript</a></li>
                <li><a href="#">jQuery</a></li>
                <li><a href="#">Node.js</a></li>
            </ul>
        </nav>
    </header>
    <div id="content">
        <section id="main_section">
            <article class="main_article">
                <h1>Main Article</h1>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur in magna libero. Sed nec pharetra nunc. Proin eget magna id ipsum eleifend cursus sit amet nec lectus. Nunc quis lacus magna. Aliquam blandit, sapien ut viverra fermentum, elit tortor ornare nisi, in luctus sem massa pulvinar turpis. Cras tincidunt dictum urna ut ultricies. Nullam diam nibh, pellentesque non laoreet ut, bibendum nec mauris. Maecenas pulvinar porttitor laoreet. Vivamus bibendum purus nisl, eget aliquam lectus. Maecenas justo libero, euismod sit amet suscipit eu, vulputate eget neque. Aliquam quam est, blandit nec iaculis non, suscipit vel nunc. Proin et odio aliquam erat pharetra accumsan et quis neque. Vivamus interdum accumsan leo eu adipiscing. Integer accumsan elit non turpis faucibus porttitor. Aliquam scelerisque nisi et turpis pretium at ultricies turpis pharetra.</p>
            </article>
            <article class="main_article">
                <h1>Main Article</h1>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur in magna libero. Sed nec pharetra nunc. Proin eget magna id ipsum eleifend cursus sit amet nec lectus. Nunc quis lacus magna. Aliquam blandit, sapien ut viverra fermentum, elit tortor ornare nisi, in luctus sem massa pulvinar turpis. Cras tincidunt dictum urna ut ultricies. Nullam diam nibh, pellentesque non laoreet ut, bibendum nec mauris. Maecenas pulvinar porttitor laoreet. Vivamus bibendum purus nisl, eget aliquam lectus. Maecenas justo libero, euismod sit amet suscipit eu, vulputate eget neque. Aliquam quam est, blandit nec iaculis non, suscipit vel nunc. Proin et odio aliquam erat pharetra accumsan et quis neque. Vivamus interdum accumsan leo eu adipiscing. Integer accumsan elit non turpis faucibus porttitor. Aliquam scelerisque nisi et turpis pretium at ultricies turpis pharetra.</p>
            </article>
            <article class="main_article">
                <h1>Main Article</h1>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur in magna libero. Sed nec pharetra nunc. Proin eget magna id ipsum eleifend cursus sit amet nec lectus. Nunc quis lacus magna. Aliquam blandit, sapien ut viverra fermentum, elit tortor ornare nisi, in luctus sem massa pulvinar turpis. Cras tincidunt dictum urna ut ultricies. Nullam diam nibh, pellentesque non laoreet ut, bibendum nec mauris. Maecenas pulvinar porttitor laoreet. Vivamus bibendum purus nisl, eget aliquam lectus. Maecenas justo libero, euismod sit amet suscipit eu, vulputate eget neque. Aliquam quam est, blandit nec iaculis non, suscipit vel nunc. Proin et odio aliquam erat pharetra accumsan et quis neque. Vivamus interdum accumsan leo eu adipiscing. Integer accumsan elit non turpis faucibus porttitor. Aliquam scelerisque nisi et turpis pretium at ultricies turpis pharetra.</p>
            </article>
        </section>
        <aside id="main_aside">
            <input id="first" type="radio" name="tab" checked="checked" />
            <input id="second" type="radio" name="tab" />
            <!-- input id 와 label for가 연결됨.-->
            <section class="buttons">
                <label for="first">First</label>
                <label for="second">Second</label>
            </section>
            <div class="tab_item">
                <ul>
                    <li class="item"><a href="#">
                        <div class="thumbnail">
                            <img src="http://placehold.it/45x45" />
                        </div>
                        <div class="description">
                            <strong>HTML5 Canvas</strong><p>2012-03-15</p>
                        </div>
                    </a></li>
                    <li class="item"><a href="#">
                        <div class="thumbnail">
                            <img src="http://placehold.it/45x45" />
                        </div>
                        <div class="description">
                            <strong>HTML5 Audio</strong><p>2012-03-15</p>
                        </div>
                    </a></li>
                    <li class="item"><a href="#">
                        <div class="thumbnail">
                            <img src="http://placehold.it/45x45" />
                        </div>
                        <div class="description">
                            <strong>HTML5 Video</strong><p>2012-03-15</p>
                        </div>
                    </a></li>
                    <li class="item"><a href="#">
                        <div class="thumbnail">
                            <img src="http://placehold.it/45x45" />
                        </div>
                        <div class="description">
                            <strong>HTML5 Semantic Web</strong><p>2012-03-15</p>
                        </div>
                    </a></li>
                </ul>
            </div>
            <div class="tab_item">
                <ul>
                    <li class="item"><a href="#">
                        <div class="thumbnail">
                            <img src="http://placehold.it/45x45" />
                        </div>
                        <div class="description">
                            <strong>CSS3 Transition</strong><p>2012-03-15</p>
                        </div>
                    </a></li>
                    <li class="item"><a href="#">
                        <div class="thumbnail">
                            <img src="http://placehold.it/45x45" />
                        </div>
                        <div class="description">
                            <strong>CSS3 Animation</strong><p>2012-03-15</p>
                        </div>
                    </a></li>
                    <li class="item"><a href="#">
                        <div class="thumbnail">
                            <img src="http://placehold.it/45x45" />
                        </div>
                        <div class="description">
                            <strong>CSS3 Border</strong><p>2012-03-15</p>
                        </div>
                    </a></li>
                    <li class="item"><a href="#">
                        <div class="thumbnail">
                            <img src="http://placehold.it/45x45" />
                        </div>
                        <div class="description">
                            <strong>CSS3 Box</strong><p>2012-03-15</p>
                        </div>
                    </a></li>
                </ul>
            </div>
        </aside>
    </div>
    <footer id="main_footer">
        <h3>HTML5 + CSS3 Basic</h3>
        <address>Website Layout Basic</address>
    </footer>
</body>
</html>
```

  white-space : 스페이스와 탭, 줄바꿈, 자동줄바꿈을 어떻게 처리할지 정하는 속성   
  overflow: hidden; - 부모보다 큰걸 안보이게 없앰.   
            오버플로우만 쓰면 실제로 한줄로 넘어가는 것이 아님.
            따라서 white-space nowrap으로 강제로 한줄로 쭉 나오게끔 해줘야 ellipsis가 먹힘.


