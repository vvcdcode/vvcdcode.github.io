---
layout: post
title:  자바스크립트와 웹 프론트엔드
date: 2019-07-22
tags: javascript
authors: seoryung
cover: /assets/post_header.png
---

## **Try! helloworld javascript**
## **2장** 자바스크립트와 웹 프런트엔드

1장에서 자바스크립트의 기본적인 문법을 배웠고 2장부터는 웹페이지의 기능을 구현하는 방법을 배운다.

 

```javascript
var newContent = prompt("자바스크립트로 html 페이지 변경하기");
document.body.innerText = newContent;
```

`prompt`는 입력 창으로 사용가가 텍스트를 입력할 수 있게 해주는 건데
두번째 줄 코드는 html 콘텐츠를 그 입력한 텍스트로 바꿔버린다. javascript가 html을 변경한 것이다. 근데 html 코드 자체가 바뀌는 것은 아니고 렌더링이 바뀌는 것 같은데 그것은 자세히 알아보기로 한다.
document 객체 안에 html의 `head`, `body`등의 모든 태그가 포함되어 있으므로 접근하거나 변경할 때 `document.querySelector("p");` 처럼 docuemnt 다음에 속성을 입력하면 된다.


`document.children[0];` : 자식 태그 접근하기<br>
`document.getElementById("idid");` : 해당 id를 가진 태그 조회

만약 id가 "lyricist"인 태그의 내용을 "Hello"로 변경하고 싶으면
```javascript
var t = document.getElementById("lyricist");
t.innerHTML = "Hello";
```

먼저 "lyricist"인 태그를 반환하고 변수 t에 저장해 조회하거나 변경한다.


CSS 역시 변경할 수 있다.
```css
t.style.color = "blue";
t.style.fontSize = "10pt";
```

`getAttribute()`<br>
`setAttribute()`<br>
`getElementByTagName()`<br>
`getElementByClassName()`<br>
`getElementByName`<br><br>

 CSS 선택자를 활용하는 법: `querySelector()`, `querySelectorAll()`<br>

`querySelector()`는 해당되는 엘리먼트 한 개만, `querySelectorAll()` 해당되는 엘리먼트를 모두 반환한다.

```javascript
document.querySelector(#songwriter);
document.querySelectorAll("p");
```

혹은 엘리먼트를 추가하거나 삭제할 수도 있다. `createElement()`, `cloneNode()`, `appendChild()`, `insertBefore()`, `removeChild`
```javascript
hr = document.createElement("hr");
document.body.appendChild(hr);
```
`createElement()`는 엘리먼트를 생성만 하는 것이고 추가하지는 않으므로 생성된 엘리먼트를 `appendChild()`로 추가한다. 혹은 특정 위치에 추가하고 싶다면 `insertBefore()`을 사용한다. 
```javascript
document.body.insertBefore(hr, document.body.children[3]);
```
`body`태그의 4번째(0부터 시작하므로) 엘리먼트 앞에 추가된다.

삭제하는 법은
```javascript
docuemnt.body.removeChild(hr);
```