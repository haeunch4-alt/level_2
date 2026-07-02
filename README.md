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
# layout 
### 수평, 수직
### flex 레이아웃 속성
#### 적용방법
1. 정렬하고자 하는 부모-자식 대상을 확인한다.
2. 2개 이상의 자식 요소가 수평,수직 어느방향으로 정렬되었는지 확인한다,
3. 부모요소에세 `display:flex`소성을 먼저 적용한다.
4. 2번에서 확인한 방향을 메인축으로 지정하고 줄바꿈을 설정한다 `flex-flow`
5. 메인축 정렬을 교차축 정렬속성을 활용하여 마무리를 진행한다.
#### 주요 속성과 주의사항, 팁
* `display:flex` : 정렬 자식등의 부모에게 설정하는 flex 시작 값 (필수)
* `flex-flow :방향 줄바꿈` : 메인축의 방향과 줄바꿈을 성정하는 묶음값 ( 필수)
* `justify-content:메인축 정렬값`
    * flex-flow에서 설정된 메인축 방향에 따라 정렬을 정하는 속성
    * 메인축 row인 경우 : 왼쪽, 가운데, 오른쪽, 양쪽끝, 균등여백
    * 메인축 cloumn인 경우 : 위, 가운데, 아래, 양쪽 끝, 균등여백
    * 양쪽,위 (flex-start), 가운데(center), 오른쪽,아래(flex-end)
    * 양쪽 끝 (space-between), 균등여백 (space-around)
* `align-content:교차축 2줄이상 정렬값` , `align-items: 교차축 1줄 정렬값`
    * flex-flow의 값이 nowrap이면 -> align-items
    * flex-flow의 값이 `wrap`이고 교차축이 2줄이상이면 -> `align-content`
    * **align-content만 space-between, space-around 값 사용가능**
    * `flex-end, flex-start, center`는 **aline-content,item 모두 사용가능**
    * `flex-flow:row nowrap; align-items:flex-end;`
        * 해석) 흐름 가로, 줄 바꿈 없음, (1줄 정렬) 교차축(세로) 아래정렬
    * `flex-flox:column wrap; align-content:center;`
        * 해석) 흐름 세로, 줄바꿈 있음, 교차축(가로) 가운데 정렬
### position
#### podition:absoluste;
* 피그마에서 **오토레이아웃무시** 기능으로 **부모프레임 위치에서 상대적으로 위치를 맞췄을 때** 사용
1. 태그 상의 부모 후보들 중에(부모, 조상 모두 포함) 원하는 기준 대상으 position속성으로 설정한다.
2. 1번 기준 성정 완료 후 실제 움직이고 싶은 대상에 absolute를 설정해서 `left, top, right, bottom` 선택옵션을 통해 위치를 이동한다.
#### position:fixed;
* 피그마에서 **오토레이아웃무시-> 프로토타입 위치(고정) -> 좌표설정** 한 경우
1. body 태그의자식 위치로 원하는 고정 목적 태그를 작성한다.
2. body는 기본 구조태그로 `position:relative;`설정이 필요없다
3. 1번에서 작성한 태그에 `position:fixed;`와 가까운 좌표값을 입력한다.
## table
### 표 HTML 작성순서와 주의사항
* `table` -> `tr` -> `td` or `th` -> 필요시 나머지태그들 
* tr 가로 1행 태그, td 내용 1열, th 제목 1열 
* 표 태그는 table을 제외하곤 크게 의미로 나누지 않아 행, 열에 클래스 또는 아이디명을 설정하지 않음. 개별 디자인시에는 CSS에서 nth 수열선택자를 사용해서 대상을 디자인해야함.
### 표 CSS 디자인 시 주의사항 
* 표는 border가 기본값 0으로 구분이 안되니 css로 구분값 적용하기
* 제목, 내용 열은 height 보다는 padding 상하값으로 상대적으로 여백 성정하기
* 1행 전체에 동일한 디자인(테두리,배경색)이 적용되어있을 땐 tr에 적용하기
* th, td열에 동시에 적용하고 싶은 디자인은 `tr > *`적용하기