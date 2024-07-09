### 이벤트
 **: 웹 페이지에서 어떠한 행위(사용자의 행동)가 발생한 것을 이벤트라 함**
 
 **활용**
 
 : 이벤트 속성과 이벤트 핸들러(함수)를 연동하여 이벤트 발생 시 특정기능을 하도록 함

이벤트 설정방법
1. **고전 이벤트 모델**
  - 요소 객체가 가지고 있는 이벤트 속성에 이벤트 핸들러를 연결하는 방법
  - 이벤트를 제거할 때는 속성값에 null값을 넣어주면 됨
2. **인라인 이벤트 모델**
  - 요소 내부에 이벤트를 작성하는 방법
  - script 태그에 있는 함수를 호출하는 방식
3. **표준 이벤트 모델**
  - w3c에서 공식적으로 지정한 이벤트
  - 한번에 여러가지 이벤트 핸들러 설정 가능

```
// 고전 방식
var btnTag = document.querySelector("#btn1");
// 동작할 코드를 가진 익명함수를 click event 속성에 바인딩해줌.
btnTag.onclick = function(){
  alert("고전 이벤트 동작");
}
```
```
// 인라인 이벤트 모델
<button onclick="inlineEvent();">인라인 이벤트 모델</button>
<span onclick="inlineEvent();">span 태그에도 바인딩 가능</span>
// 인라인 이벤트에 쓰일 함수
function inlineEvent(){
  alert("인라인 이벤트 동작");
}
```
```
// 표준 이벤트 모델
var sBtn1Tag = document.querySelector("#sBtn1");
sBtn1Tag.addEventListener("click", ()=>{
  alert("표준 이벤트 동작!");
});
```




