# HTML
Key Word : 
<hr/>

## HTML 태그!
   
  **오늘의 예제 1**
  
  ![image](https://user-images.githubusercontent.com/84966961/121777737-9e08a400-cbce-11eb-84db-01b4c3c9e985.png)

```
<body>
    <div>
    <fieldset>
        <h2>프런트엔드 개발자 지원서</h2>
        <p>HTML, CSS, Javascript에 대한 기술적 이해와 경험이 있는 분을 찾습니다.</p>
        <hr>
        <form action="submit.html">
        <dl>
            <dt><b>개인정보</b></dt><br>
            <dd><label for="name"> 이름 <input type="text" placeholder="공백없이 입력하세요." name="id" id="id"></label></dd>
            <dd><label for="tel"> 연락처 <input type="tel" placeholder="010-****-****" name="tel" id="tel"></label></dd>
        </dl>
        <dl>
            <dt><label for="objective"><b>지원 분야</b></dt><br>
            <dd><input type="radio" name="hobby" id=""> 웹퍼블리싱</dd>
            <dd><input type="radio" name="hobby" id=""> 웹 애플리케이션 개발</dd>
            <dd><input type="radio" name="hobby" id=""> 개발 환경 개선 </label></dd>
        </dl>
        <label for="motiv"><b>지원 동기</b><br><br>
        <textarea name="" id="" cols="60" rows="7" placeholder="본사 지원 동기를 간략히 써 주세요."></textarea></label><br>
        <input type="submit" value="접수하기" name="" id=""> <input type="reset" value="다시 쓰기" name="" id=""><br>
    </form>
    </fieldset>
</div>
</body>   
```
  **오늘의 예제 2**   
   
  ![image](https://user-images.githubusercontent.com/84966961/121779067-d57a4f00-cbd4-11eb-9886-9b58646554e3.png)

```
<body>
    <p>이 것은 파랑색 디폴트 색</p>
    <form action="intro(이동욱).html">
        <!--action 란에는 input 값을 처리할 subpage를 넣는다.-->
        <fieldset>
            <legend>개인정보</legend>
            <label for="id">아이디</label><input type="text" name="id" value="" autofocus placeholder="영문자숫자조합" readonly
                required><br>
            <!--name 속성 : 백엔드에서 처리를 위한 용도 paramiter 그릇, 그룹화를 위한 용도
                value : 입력창에 실제 값을 넣는 것과 같은 효과 / 백엔드에서 처리될 때 불러오는 값(특히나 select_option태그에서)
                autofocus 커서가 자동으로 갈 공간, 페이지당 한곳만 지정 가능
                placeholder 필요한 요구사항 작성 가능. 낮은 투명도로 공란에 표시됨. 예시용
                readonly 단순 읽기용 - 회원정보 수정창에서 변경이 안되는 항목.
                required 필수 기입-->
            <label for="password">패스워드</label><input type="password" name="password" id="" size="10"><br>
            <label for="address">주소</label><input type="text" name="address" id="" size="50"><br>
            <!--size 창의 크기 (default 값 = 20자) 줄이는 것도 가능.-->
            <hr>
            <label for="hobby">취미 <br>
                <!--name 속성 : 백엔드에서 처리를 위한 용도 paramiter 그릇, 그룹화를 위한 용도-->
                <input type="radio" name="hobby" id="" checked> 운동 <br>
                <!--checked : 체크가 되어 있는 상태로 시작.-->
                <input type="radio" name="hobby" id=""> 음악감상 <br>
                <input type="radio" name="hobby" id=""> 독서 <br>
            </label>
            <hr>
            <label for="">수강과목 <br>
                <input type="checkbox" name="" id=""> java <br>
                <input type="checkbox" name="" id=""checked> css <br>
                <input type="checkbox" name="" id=""> sql <br>
            </label>
            <hr>
            <label for="">직업</label>
            <select name="" id="">
                <option value="1">직업선택</option>
                <option value="2">개발자</option>
                <option value="3">의사</option>
                <option value="4">기사</option>
            </select><br>
        </fieldset>
        <label for="">전달메세지</label><br>
        <textarea name="" id="" cols="30" rows="10"></textarea>
        <input type="hidden" name="as" id=""><br>
        <label for="">메일</label><input type="email" name="mail" id=""><br>
        <label for="">숫자입력</label><input type="number" name="" id=""><br>
        <label for="">전화번호</label><input type="tel" name="" id=""><br>
        <label for="">시간</label><input type="time" name="" id=""><br>
        <label for="">색상선택</label><input type="color" name="" id=""><br>
        <label for="">날짜출력</label><input type="date" name="" id=""><br>
        <label for="">시간</label><input type="datetime" name="" id=""><br>
        <label for="">로컬시간</label><input type="datetime-local" name="" id=""><br>
        <input type="submit" name="" id=""><input type="reset" name="" id=""><br>
        <input type="button" value="경고메세지" onclick="alert('메세지출력')" name="" id=""><br>
        <input type="image" src="images/orange.jpg" width="300" name="" id=""><br>
    </form><br>
    <dl>
        <dt>hello:</dt>
        <dd>안녕하세요 이동욱입니다.</dd>
        <dd>유의어 : </dd><!--몇개들어가든 상관이없음. 계층구조로 들여쓰기됨.-->
    </dl>
</body>
```
   
 1강에서 배운 개념과 예제 태그와 더불어 다른 태그들에 대해 정리해보려고 한다.

 ### paragraph 태그   
```  
		<p>first paragraph</p>
		<p>second paragraph</p>
		<p>
			new line<br>
			third paragraph
		</p>
 ```
    
 p 태그는 문단 태그로서 p 태그 안의 내용을 중심으로 위아래 공백 라인을 잡아준다.

 ### hr 태그    
   
 hr 태그는 수평선을 그려주는 태그로서 css를 통해 다양한 디자인 값을 줄 수 있음.   
    
```css
hr.two{width: 500px;color:red;border: thin solid red;}
hr.two_1{width: 500px;border-bottom:0px; text-align:left; margin-left: 0px;}
hr.three{height: 50px;}
hr.three_1{height: 50px; width:0px;border-right:0px;}
hr.four{border:none;}
hr.five{border:none; border:1px dashed blue;}
hr.six{border:none; border:5px double orange;}
```
   **예시 화면**
![image](https://user-images.githubusercontent.com/84966961/121777572-d5c31c00-cbcd-11eb-8a42-9e9a8f8f6742.png)   
   
 ### form 태그 
 ```
<form action="submit.html">
        <dl>
            <dt><b>개인정보</b></dt><br>
  ...
```
  오늘의 예제에서는 form 태그에 action을 주어 제출시 submit 파일로 넘어가도록 링크를 걸어 놓았다.    
    
 form 태그는 사용자 의견이나 정보를 알기 위해 입력할 큰 틀을 만드는 데 사용되는 태그이다. 폼은 입력된 데이터(주로 input 태그에 담긴 정보들)를 한 번에 서버로 전송한다. 전송한 데이터는 웹 서버가 처리하고, 결과에 따른 또 다른 웹페이지를 보여준다. 오늘의 예시에서는 제출 처리로 summit.html 파일로 이동되도록 설정되어있다.


 ### 목록을 만드는 dl(Definition list), dt(Definition Term), dd(Definition Description) 태그    
   
```
        <dl>
            <dt><b>개인정보</b></dt><br>
            <dd><label for="name"> 이름 <input type="text" placeholder="공백없이 입력하세요." name="id" id="id"></label></dd>
            <dd><label for="tel"> 연락처 <input type="tel" placeholder="010-****-****" name="tel" id="tel"></label></dd>
        </dl>
        <dl>
            <dt><label for="objective"><b>지원 분야</b></dt><br>
            <dd><input type="radio" name="hobby" id=""> 웹퍼블리싱</dd>
            <dd><input type="radio" name="hobby" id=""> 웹 애플리케이션 개발</dd>
            <dd><input type="radio" name="hobby" id=""> 개발 환경 개선 </label></dd>
        </dl>
```
![image](https://user-images.githubusercontent.com/84966961/121777894-4c144e00-cbcf-11eb-92cd-3395406ed59b.png)
   
 그림의 모습처럼 사용하기 위해서 dl 태그로 묶어주고 내용에 dt와 dd를 넣어주면된다.   
 dt는 Definition Term(정의 용어)의 약자로 정의되는 용어의 제목을 넣을때 사용한다.
 dd는 Definition Description(정의 설명)의 약자로, 용어를 설명하는 데 사용한다.   
    
 하지만 오늘의 예제에서는 지원자의 정보를 수집하기 위한 틀로써 사용되었으며 dd 내부에는 제목을 넣는 label 태그와 input 태그를 다양한 값을 제공받고자 넣어주었다. dd 태그는 자동으로 들여쓰기가 되며 들여쓰기 거리를 조절하려면 text-indent 속성이나 margin 혹은 padding left 값을 조절하여 사용할 수 있다.   
    
 dd는 계층 구조로 쓰이는 것이다.   
   
  ### 폼의 양식에 이름을 붙이는 label 태그

```
        <form action="submit.html">
        <dl>
            <dt><b>개인정보</b></dt><br>
            <dd><label for="name"> 이름 <input type="text" placeholder="공백없이 입력하세요." name="id" id="id"></label></dd>
            <dd><label for="tel"> 연락처 <input type="tel" placeholder="010-****-****" name="tel" id="tel"></label></dd>
        </dl>
		...
```
   
 위의 예시 코드에서 label은 form 태그 내부에 존재하며 input 태그를 예시처럼 내부에 넣게되면 for 속성을 통해 서버 처리시 자동 연동이 된다.   
     
 label의 for 속성과 input의 id 값이 같다면 또한 연동 될 수 있다.

  #### input 태그   
   
 input 태그는 form 태그 안에서 추가되는 입력 요소들 중 가장 중요한 태그이다. input 태그는 사용자로부터 정보를 받아들이는 용도로 사용되는데 input 태그의 type 이라는 속성을 이용해 입력 양식을 여러가지로 변경하여 사용된다.   
   
 **type 속성 종류**

|type 속성값|속성정보|
|------|------|
|text|텍스트를 입력하는 창을 생성합니다.|
|password|비밀번호를 입력하는 창을 생성합니다.|
|radio|라디오 버튼을 생성합니다.(동그란 체크박스)|
|checkbox|체크박스를 생성합니다.(토글형 체크박스)|
|file|파일 이름을 입력하는 창을 생성합니다.|
|image|이미지를 전송 버튼으로 만듭니다.|
|hidden|사용자에게 보이지는 않지만 서버로 전송됩니다.|
|submit|서버로 제출/전송하는 버튼을 만듭니다.|
|button|일반 버튼을 생성합니다.|
|reset|페이지 초기화를 합니다.|

 #### text 타입 설명   
 
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













