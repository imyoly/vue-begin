# vue-begin


/* common */
* {color: #3A3A3A;}
a {text-decoration:none; }
a:hover { text-decoration: none; }
a:focus { text-decoration: none; }
a:visited {text-decoration: none; }

ul {margin: 0; list-style:none; padding-inline-start: 0;}
.btn {
  width:40px;
  text-align: center;
  padding: 3px;
  margin-left: 6px;
  border-radius: 20px;
  border: 2px solid #FBCC03;
  background-color: #FBCC03;
  font-weight: 800;
  box-shadow: 2px 2px 4px rgba(177,164,140,0.64);
  float:right;
  font-size: 15px;
}


#app {padding: 30px 30px; z-index: 1;}
#app::after {
    content: '';
    display: block;
    width: 3000px;
    height: 3000px;
    position: absolute;
    top: -20%;
    right: -15%;
    background-color: rgba(251,204,3, 0.7);
    border-radius: 50%;
    transition: all 0.8s;
    transform: scale(0.5);
    transform-origin: top right; 
}

/* header */
#header {display:flex; justify-content: space-between; margin-top: 5px; font-family: 'Archivo Black', sans-serif; font-family: 'Open Sans', sans-serif;vertical-align: middle;}
.header-title { margin: 0 10px; font-size: 40px; font-weight: 800;}
.header-title a {border-bottom: 1px solid  #FFDF24; box-shadow: inset 0 -7px 0 #FFDF24; transition: background 0.15s cubic-bezier(0.33, 0.66, 0.66, 1) 0s;}
.header-title a:hover { background-image: linear-gradient(#fff 50%, #FFDF24 50%);}
.header-nav { margin-left: 50rem; width:400px; font-size: 19px; font-weight: 400; z-index:2;}
.header-nav ul {display: flex; justify-content: space-between;}
.menu {margin-top: 17px; }
.menu a {color: #707070;}
.menu a:hover {color: #3A3A3A; font-weight: 800;}
.header-test { z-index:2; }

.header-test a {margin-right: 2rem; font-size: 40px; font-weight: 800;}
.header-test a:hover { color: #707070; font-weight: 400;}


/* container */
#container { padding: 30px 70px;position: relative; z-index:3;background: #fff; margin: 40px 10px; padding: 10px 25px 30px 25px; border-radius: 10px; width: 100% ; height: 100% ; box-shadow: 0 0 21px 0 rgba(0,0,0,0.3); z-index:3; }
/* .left-content { margin: 20px 10px; padding: 30px 25px; border-radius: 10px; width: 80px; height: ; box-shadow: 0 0 8px 0 rgba(0,0,0,0.1);  } */
.date { margin-bottom: 0; font-size: 50px; font-weight: 800;display: inline-block;text-align: center;}
.title { margin-top: 0;font-size: 90px; font-weight: 800; color : #d4ba27; }
/* .title::before {
    content: "";
    border-radius: 50%;
    display: inline-block;
    margin-right: 10px;
    width: 30px;
    height: 30px;
    background-color: #FBCC03;
} */
.container-title {margin: 0px 30px;}
.container-content { margin: 80px 60px 30px 30px; padding: 30px 25px; border-radius: 20px; width: 500px; height: 500px; box-shadow: 0 0 8px 0 rgba(0,0,0,0.1);  }


/* footer */
#footer {z-index:3; position: absolute; bottom: 0; padding-top : 20px; width: 100%; height: 40px; border-top: 1px solid rgba(0,0,0,0.1);  text-align: center; font-size: 14px;}

-- index.html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Archivo+Black&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Archivo+Black&family=Open+Sans:wght@300;400;800&display=swap"
      rel="stylesheet">
    <link rel="stylesheet" href="./src/common.css">
    <title>vue-todo</title>
  </head>
  <body>
    <div id="app">
    </div>
    <script src="/dist/build.js"></script>
  </body>
</html>

-- app.vue
<template>
    <div id="app">
      <div id="header">
          <h1 class="header-title">
            <a href="">Begin</a>
          </h1>
          <div class="header-nav">
                <ul>
                  <li class="menu"><a href="#">summary</a></li>
                  <li class="menu"><a href="#">code</a></li>
                  <li class="menu"><a href="#">sample</a></li>
                  <li class="menu"><a href="#">sample</a></li>
                </ul>
          </div>
          <div class="header-test">
              <a href=""><span>+</span></a>
          </div>
      </div>

      <div id="container" style="display:inline-block">
          <div class="container-title" style="display:inline-block; line-height: 50px; margin-top: 40px;" >
              <p class="date"> Thursday, 10th </p><span class="btn">Dec</span>
              <h2 class="title" >TODAY <span>is</span></h2>
              <p>라라라라라랄ㄹ라ㄹ</p>
          </div>
          

          <div class="container-content" style="float:right">
            가운데
            <TodoHeader></TodoHeader>
            <TodoInput></TodoInput>
            <TodoList></TodoList>
            <TodoFooter></TodoFooter>
          </div>
      </div>

      <div id="footer">footer</div>
    </div>
</template>

<script>
// # 특정 컴포넌트에서 다른 위치에 있는 컴포넌트의 내용을 불러올 때(ES6 import 구문)
// import 불러온 파일의 내용이 담길 객체 from '불러올 파일 위치';

import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from './components/TodoFooter.vue'

// import '.'

export default {
  components: {
    // 컴포넌트 태그명 : 컴포넌트 내용 (import 객체)
    'TodoHeader' : TodoHeader,
    'TodoInput' : TodoInput,
    'TodoList' : TodoList,
    'TodoFooter' : TodoFooter
  }

}
</script>

<style>

</style>
