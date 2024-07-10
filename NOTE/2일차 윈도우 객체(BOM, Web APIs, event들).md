## 윈도우 객체

### window 객체는 자바스크립트의 최상위 객체이며, BOM, DOM으로 나뉜다

### 브라우저 창에 대한 설정을 하는 객체

1. alert
```
window.alert(message);
```
2. confirm
```
window.confirm(message); // return boolean
// 확인 -> true / 취소 -> false
```
3. prompt
```
window.prompt(inputMessage);
// 입력창에 값을 입력 ( 변수에 저장해서 활용 가능 )
```
4. open
```
window.open(url, name, option);
// _blank : 새 창으로 연다. (기본값)
//  _parent : 부모 프레임에 열린다.
//  _self : 현재 페이지를 대체한다.
//  _top : 로드된 프레임셋을 대체한다.
//  name(임의의 이름) : 새 창이 열리고 창의 이름을 지정한다. 
// 동일한 이름에 다시 open() 을 하면 기존의   열린창의 내용이 바뀐다. 다른 이름을 사용하면 또다른 새창이 열린다.

```
5. close
```
// myWindow = window.open(url,name,option);
myWindow.close();
// 해당 창 닫음
```
6. setTimeout
```
window.setTimeout(()=>{}, msec);
// 일정 시간 이후 동작
// 매개변수로 함수의 참조를 전달
```
7. setInterval
```
var myInterval = window.setInterval(function(){}, msec);
// 일정 시간마다 반복 동작
//함수의 참조를 전달

```
**주의❗❗❗**

*setInterval()을 반복 실행할 경우 변수에는 마지막에 실행된 객체가 들어가있으며
 그 전에 실행된 각 객체들은 브라우저의 런타임 환경에서 실행되고 있음.
 변수를 통해 접근 불가능하기 때문에 동작이 중복되지 않도록 주의!*
 


8. clearInterval
```
// myInterval = window.setInterval(...);
window.clearInterval(myInterval);
```

9. 디지털 시계 예시
```
function startClock(){
    clockTime = window.setInterval(()=>{
    var hour = new Date().getHours();
    var min = new Date().getMinutes();
    var sec = new Date().getSeconds();
    clockDiv.innerText = `${hour}:${min}:${sec}`;
  }, 1000);
}
```
Date 객체를 생성해 메소드를 이용하여 각 시간, 분, 초를 계산해줄 수 있음.


## navigator 객체
웹 페이지를 실행하고 있는 브라우저에 대한 정보를 가지고 있는 객체
**navigator.userAgent** -> 웹 브라우저를 식별할 수 있는 정보💥💥 상식❗❗



## screen 객체
웹 브라우저 화면이 아닌 운영체제 화면의 속성을 가진 객체


1. screen 객체
properties : 
	availHeight
	availLeft
	...
	width
	heigth
	...
screen 객체의 속성들을 이용하여 화면의 너비와 높이를 가져와 띄우고자 하는 창의 위치를 조정해줄 수 있었음.	
```
var left = (screen.width - 500)/2;
var top = (screen.height - 600)/2;
myWindow = window.open("./2.JS_DOM.html","pop",`width=500,height=600, left=${left}, top=${top}`);
// open(url, name, option)의 option값에 left, top 값 지정         
```

## location 객체
 1.href : 속성값 이용한 페이지 이동
 ```
 location.href = "http://www.naver.com"
 ```

 2.assign(url) : 전달값 이용한 페이지 이동
 ```
 location.assign("http://www.naver.com");
 ```
 
 3.replace(url) : (뒤로가기 불가능) 전달값 이용한 페이지 이동
 ```
 location.replace("http://www.naver.com");
 ```
 

## history 객체
현재 창에서 사용자의 방문 기록을 저장함.
뒤로가기(-1), 앞으로가기(1), 새로고침(default) 가능

 *go(num) : 
 ```
 history.go();
 ```
	default - 새로고침
	-1 - 뒤로가기
	1 - 앞으로 가기
 



### 💥💥addEventListener에 전달되는 함수 💥💥
addEventListenr(event, functionName)
function의 이름이나 직접 함수를 정의하는 코드를 적어야 됨.
만약 function()의 형태로 호출하는 코드를 넣게 되면 함수를 호출한 후 return값을 전달하게 됨.

addEventListener엔 함수의 참조를 전달해줘야 함!!

ex)
addEventListener(event, func()); => func함수에 구현되어 있는 코드 실행 및 return값 전달 (만약, return값이 함수의 참조가 아니라면 문제 발생)

=> 이벤트가 발생했을 때 참조할 함수를 전달해야 하는것!!!
만약 함수의 참조를 return하는 함수라면 함수 호출 코드 써도 됨.                            
(*단, 호출함수(그 안의 로직이) 먼저 즉시 실행된다는 점 기억!*)
