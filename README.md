# PALLAX
![p1](https://github.com/hyeonbeen97/pallax/assets/125417850/db7431bc-791b-45fc-9cff-90bcc304b9bc)


## 소개
이 웹 사이트는 멋진 패럴럭스(Parallax) 효과를 활용하여 디자인된 웹 페이지입니다. 패럴럭스 효과는 스크롤을 내리면서 배경과 컨텐츠의 움직임을 다르게 함으로써, 웹 페이지가 더 동적이고 생동감 있는 느낌을 줍니다.

이 사이트는 총 9개의 섹션으로 구성되어 있으며, 각 섹션은 다양한 이미지와 텍스트로 구성되어 있습니다. 페이지 상단에는 메뉴가 위치하고 있어서 사용자가 원하는 섹션으로 쉽게 이동할 수 있습니다. 스크롤을 내릴 때마다 페이지 우측에는 scrollTop 값이 실시간으로 표시되어, 사용자가 현재 스크롤 위치를 확인할 수 있도록 되어 있습니다.

패럴럭스 효과와 함께 사용된 다양한 텍스트와 이미지들은 각각의 메시지와 의미를 전달하며, 페이지가 아름답게 조합되어 독특하고 매력적인 디자인을 형성하고 있습니다.

## 사용스택
● window.addEventListener("scroll", () => { ... }): 페이지 내에서 스크롤 이벤트를 감지하는 이벤트 리스너입니다. 스크롤이 발생할 때마다 해당 함수가 호출되며, scrollTop 변수에 현재 스크롤의 수직 위치를 저장합니다.

● let scrollTop = window.pageYOffset || window.scrollY || document.documentElement.scrollTop;: scrollTop 변수에 현재 스크롤 위치를 할당합니다. 이때, 크로스 브라우징을 고려하여 여러 프로퍼티(window.pageYOffset, window.scrollY, document.documentElement.scrollTop)를 사용하여 스크롤 위치를 얻어옵니다.

● document.querySelector(".scroll span").innerText = parseInt(scrollTop);: 페이지 내에서 .scroll 클래스를 가진 요소의 <span> 태그에 scrollTop 값을 표시합니다. 이로써 현재 스크롤 위치를 실시간으로 확인할 수 있습니다.

스크롤 위치에 따른 메뉴 활성화:

● document.querySelectorAll(".parallax__item").forEach((item, index) => { ... }): .parallax__item 클래스를 가진 요소들을 찾아서 각 요소의 위치 정보를 확인합니다. 스크롤 위치(scrollTop)와 각 요소의 위치 정보를 비교하여, 현재 보여지고 있는 섹션에 해당하는 메뉴를 활성화합니다.
● document.querySelectorAll(".parallax__nav li").forEach((li) => { li.classList.remove("active") });: 메뉴들의 활성화 클래스인 active를 모두 제거합니다.
● document.querySelector(".parallax__nav li:nth-child(" + (index + 1) + ")").classList.add("active"): 현재 보여지고 있는 섹션에 해당하는 메뉴에 active 클래스를 추가하여 활성화 표시를 합니다.
메뉴 클릭시 해당 섹션으로 스크롤 이동:

● document.querySelectorAll(".parallax__nav li a").forEach((li) => { ... }): .parallax__nav li a 태그들을 찾아서 각 메뉴에 클릭 이벤트 리스너를 할당합니다.
● e.preventDefault();: 메뉴를 클릭했을 때, 기본 동작인 링크 이동을 방지합니다.
● document.querySelector(li.getAttribute("href")).scrollIntoView({ behavior: "smooth" }): 메뉴의 href 속성 값을 사용하여 해당 섹션의 요소를 찾고, 스크롤 이벤트에 의해 해당 섹션으로 부드럽게 스크롤 이동합니다.
이 스크립트는 웹 페이지의 스크롤 위치에 따라 동적으로 정보를 업데이트하고, 메뉴를 활성화하여 사용자에게 시각적인 피드백을 제공하는 역할을 합니다.
