### DOM(Document Object Model)
문서객체 : HTML에 있는 태그를 객체화하여 자바스크립트에서 다룰 수 있게 한 것, 모든 노드 객체에 접근할 수 있는 요소와 메소드를 제공함.

### 자바스크립트를 이용한 HTML태그 접근
자바스크립트를 이용하여 HTML태그를 동적으로 처리하기 위해서는 DOM객체의 메소드를 호출하여 접근해야 함



### 메소드(명령어)
1. getElementById("아이디 값")
2. getElementByName("이름값")
3. getElementByTagName("태그명")
4. **querySelector("선택자")**
5. **querySelectorAll("선택자")**

**=> querySelector를 많이 쓰는 추세**
```
//ex)
var p3Tag = document.getElementById("p3");  // id가 p3인 요소 접근
p3Tag = document.querySelector("#p3"); // 선택자를 통해 요소 접근
```
### querySelectorAll() 의 반환값
document.querySelectorAll() 메서드는 CSS 선택자에 일치하는 모든 요소를 **NodeList**로 반환한다.
NodeList는 배열과 유사하지만 정확히 배열은 아니며, 배열 메서드의 일부만을 지원한다.
필요 시 NodeList를 실제 배열로 변환하여 배열 메서드를 사용할 수 있다.

NodeList -> 배열 로 바꾸는 법

 **1. Array.from()** : 
 ```
 const nodeList = document.querySelectorAll('p');
 const array = Array.from(nodeList);
```
**2. 스프레드 연산자**  :
```
const nodeList = document.querySelectorAll('p');
const array = [...nodeList];
```

innerHTML VS innerText 
element.innerHTML = "";
element.innerText = "";

**innerHTML**: 
요소의 HTML 콘텐츠를 가져오거나 설정하는 프로퍼티로, HTML을 포함한 모든 자식 요소를 조작할 수 있다.

**innerText**: 
요소의 텍스트 콘텐츠를 가져오거나 설정하는 프로퍼티로, HTML 태그를 무시하고 텍스트만을 다룬다.

=> HTML 콘텐츠의 동적 변경이 필요한 경우에는 innerHTML을 사용하는 것이 유용할 수 있다.



## DOM 활용 예제

var tag = document.querySelector("");
태그의 속성값 바꾸는 법
tag.setAttribute("attribute", "value");
input태그의 value값 바꾸는 법
tag.value = "바꿀 value";

input 태그의 type값 바꾸는 법
tag.type = "바꿀 타입";

태그의 style속성 바꾸는 법 
tag.style.width = "";
tag.style.color = "";

input type="text" 태그의 글자 수 제한 설정
tag.size = 숫자;

