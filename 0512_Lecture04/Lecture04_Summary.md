# HTML & CSS   
Key Word :   
   
<hr/>
   
## position : fixed   

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







