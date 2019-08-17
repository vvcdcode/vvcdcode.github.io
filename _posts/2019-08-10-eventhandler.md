---
layout: post
title: 이벤트 핸들러
date: 2019-08-10
tags: javascript
authors: ryuchoi
cover: /assets/post_header.png
---


## 13. 이벤트와 자바스크립트
* **callback 함수**

    callback 함수의 개념이 약간 헷갈렸는데 쉽게 말해서 나중에 호출되는 함수이다. 다른 함수나 이벤트에 의해 호출되는 함수를 말한다.<br><br>

`setTimeout()`과 `setInterval()`은 시간을 설정해 두고 콜백 함수를 호출하는 함수이다.

`setTimeout()`: 설정한 시간이 지나면 함수 호출<br>
`setInterval()`: 설정한 시간마다 함수 호출

```javascript
setTimeout(callback, 3000);
setInterval(callback, 5000);
```
`setTimeout(callback, 3000);`은 'callback' 이라는 함수를 3초 _(밀리초 단위로 입력하므로 3000을 입력하면 3초 뒤가 된다)_ 후에 실행한다. `setInterval(callback, 5000);`은 callback() 함수를 5초마다 실행한다.


취소할 수도 있다.<br>
`clearTimeout()`은 `setTimeout()`으로 예약된 함수를 취소한다. 단 콜백 함수가 실행되기 전에 호출해야 한다. 
`clearInterval(ID)`는 `setInterval()`함수로 실행되는 함수를 취소한다. 함수를 실행했을 때 반환된 ID를 인자로 입력해야 한다.
<br><br>

### **html 태그 속성에 이벤트 핸들러 추가하기**

```html
<h1 onclick = "console.log('clicked');">이벤트 핸들러 추가하기</h1>
<input type = "text" onchange = "console.log('changed');" onkeydown = "console.log('typed');">
```

`onclick`: html 엘리먼트를 마우스로 클릭했을 때 호출된다. 위에서는 `<h1>`엘리먼트를 클릭하면 콘솔에 'clicked'가 출력된다.<br>
`onchange`: form 엘리먼트의 내용이 변경되었을 때 호출된다. 입력 폼에 내용을 입력하거나 수정하고 나오면 'changed'가 출력된다. <br>
`onkeydown`: 키보드의 키가 눌렸을 때 호출된다. 입력 폼에 글자를 입력하거나 지우는 등 키보드가 눌릴 때마다 'typed'가 출력된다.

<br>

### **자바스크립트에서 이벤트 핸들러 설정하기**

```html
<body>
        <form method ="GET" action = "b.html" id ="form1" onsubmit="console.log('form tag'); return false;">
            이름: <input type="text" name = "id"><br>
            메시지: <input type="text" name = "msg"><br>
            <input type = "submit">
        </form>
        <script>
            var t = document.getElementById("form1");
            t.onsubmit = function a () {
                console.log("from property");
                return false;
            }
            function b() {
                console.log("from addEventListener");
                return false;
            }
            function c() {
                console.log("from addEventListener-2");
                return false;
            }
            t.addEventListener('submit', b);
            t.addEventListener('submit', c);

            t.removeEventListener("submit", b);
        </script>
    </body>
```

`<form method ="GET" action = "b.html" id ="form1" onsubmit="console.log('form tag'); return false;">`처럼 form 태그에 직접 등록할 수도 있고 `<script>`태그 안에 자바스크립트 코드를 작성할 수도 있다. `input` 엘리먼트의 제출버튼을 누르면 `onsubmit` 이벤트 핸들러가 실행된다. `addEventListener()` 메서드를 사용할 수도 있는데 다른 이벤트 핸들러와 충돌하지 않아 여러 개 추가할 수도 있다.

삭제하는 방법은 `removeEventListener()`

<br>

## 14. 네트워킹
### **Ajax 요청 보내기**

Ajax (Asynchronous Javascript and XML):
비동기적 자바스크립트와 XML<br>
(Ajax에 대해 더 알아보기: https://joshua1988.github.io/web-development/javascript/javascript-asynchronous-operation/)<br>

비동기적 자바스크립트는 시간이 걸리거나 시간차를 두고 동작하는데 그 부분의 코드가 끝날 때까지 기다리지 않고 다음 코드를 실행한다. 


```html
<html>
    <head>
        <meta charset="utf-8">
        <script>
            var req = new XMLHttpRequest();
            req.open("GET", "./data.txt");
            req.send();
        </script>
    </head>
</html>
```

`open()` 데이터를 가져올 서버 설정<br>
`send()` 요청 보내기

___
*여기부터 갑자기 너무 어려워서 정신을 잃을 뻔했는데 정리하면서 다시 읽어보니 다행히 이해가 되었다. 코드는 파이썬에서 파일 생성했던 것과 비슷해서 조금 더 이해하기 쉬웠다.(쉽진 않았음)*
___


<br>

### **JSON**
JSON (Javascript Object Notification): 자바스크립트 객체를 문자열로 표현한다.
서버와 브라우저에서 데이터를 전달할 때 JSON을 사용한다.
서버에서 데이터를 JSON으로 전송하고 브라우저는 데이터를 파싱(parsing, 문자열로 된 데이터를 객체로 구성해 줌)해 반영한다.
<br>
<br>
___
 *난 이 책의 예제를 잘 모르겠다.. 개념이 어려운 것에 반해 예제에서 별다른 걸 하지 않아서 잘 와닿지 않는다. 쉽게 다루려면 어쩔 수 없었겠지만 배우는 사람은 조금 아쉬운 것이다. 이해하긴 했는데 딱히 별 의미가 없어서 따로 적지 않는다.*
 ___

<br>

## 15. 그 외

자바스크립트 코드의 위치에 따라 실행 순서가 달라진다. html 엘리먼트를 자바스크립트에서 활용하려면 스크립트보다 먼저 파싱되어야 한다.

```html
<html>
    <head>
        <meta charset="utf-8">
        <link rel = "stylesheet" herf ="css.css">
        <script>
            function check(n) {
                var sum = 0;
                for (var i = 0; i < 20000000; i++) {
                    sum += n;
                }
                alert(n);
                console.log(n);
                console.log(document.getElementById("songwriter"));
                console.log(document.getElementsByClassName("lyric"));
            }
            check(1);
        </script>
    </head>
    <body>
        <script>check(2);</script>
        <h1>애국가</h1>
        <p id = "songwriter">작곡: 안익태</p>
        <p id = "lyricist" style="color: red;" >작사: 미상</p>
        <script>check(3);</script>
        <h2>1절</h2>
        <p class="lyric">
            동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세<br>
            무궁화 삼천리 화려강산 대한사람 대한으로 길이 보전하세
        </p>
        <script>check(4);</script>
        <h2>2절</h2>
        <p class="lyric">
            남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세<br>
            무궁화 삼천리 화려강산 대한사람 대한으로 길이 보전하세
        </p>
        <script>check(5);</script>
    </body>
</html>
```

`check(5)`에서 모든 엘리먼트가 반환된다. callback 함수로 등록해 마지막에 실행되도록 하는 방법도 있다.