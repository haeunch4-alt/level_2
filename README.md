# HTML+CSS 26/06/22~
## HTML, CSS 로 웹&앱 문서 제작하는 순서
1. 제작 문서에 맞게 의미있는 HTML 태그 구성하기
2. CSS 파일을 styles 폴더에 별도로 생성하기
3. 1번에서 제작한 태그 중 디자인하려는 대상 확인하기
4. 3번 대상을 선택자로 작성하고 디자인 목적에 맞게 속성:값 작성하기
## 선택자 {속성:값;}
## 선택자 {속성:값; 속성:값;} 
# 선택자 종류
## 태그 선택자
* 태그명을 선택자로 사용하는 선택자 
* `<h1></h1>` -> `h1 {속성:값;}`
## 클래스 선택자
* 반복되는 클래스명을 사용하는 선택자
* `<h1 class="title"></h1>` -> `.title {속성:값;}`
## 자식 선택자
* 특정부모 안 자식을 사용하는 선택자
* `<h1><span></span></h1>` -> `h1 > span {속성:값;}`
## 형제 선택자 + or ~
* `<div> <a>1</a> <em>2</em> <del>3</del> </div>`
* `div> a + em {}` 해석 ) 부모 div의 자식 a의 인접형제 em 선택
* `div > a ~ del {}` 해석) 부모 div 의 자식a의 형제 del 선탣
* `+` 는 바로 옆에 있는 형제 태그만 인식한다.
* `~`은 바로 옆 형제 포함 그 뒤에 모든 형제태그들을 인식한다.
# 자주 쓰는 웹 글꼴 주소 
## 노토산스 Noto sans kr
* <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100..900&display=swap" rel="stylesheet">
## 프리텐다드 pretendard
* <link rel="stylesheet" as="style" crossorigin href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard-dynamic-subset.min.css" />