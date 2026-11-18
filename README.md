# 06. CSS의 기본

- Cascading Style Sheet
- HTML은 텍스트나 이미지, 표 같은 요소를 웹 문서에 넣어 뼈대를 만드는 역할
- CSS는 텍스트나 이미지, 배경의 크기나 배치 방법 등의 요소의 디자인 담당

## 06-2. 스타일과 스타일 시트

### 스타일 형식

```css
선택자 {
  속성1: 속성값1;
  속성2: 속성값2;
  ...
}
```

### 스타일 시트

- 스타일 규칙을 한눈에 확인하고
- 필요할 때마다 수정하기 쉽도록 **한군데 묶어 놓은 것**

- 웹 브라우저에 기본으로 만들어져 있는 **브라우저 기본 스타일**
- 사용자 스타일
  - **인라인 스타일** - 스타일 시트를 사용하지 않고 적용할 대상에 직접 표시

    ```html
    <p style="color: red">
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nesciunt quidem
    </p>
    ```

  - 내부 스타일 시트
    - html 문서 내부에 head 태그 안에 작성

      ```html
      <style>
        p {
          text-align: center;
          color: blue;
        }
      </style>
      ```

  - **외부 스타일 시트** - 연결 head 태그 안에
    - 여러 웹 문서에서 사용할 스타일을 별도 파일로 저장
    - 필요할 때마다 가져와서 사용
    - 따로 저장해 놓은 스타일 정보를 외부 스타일 시트
    - 확장자는 **.css**

    ```html
    <!-- 외부 스타일 시트 연결 -->
    <link rel="stylesheet" href="css/style.css" />
    ```

    - css/style.css

    ```css
    h1 {
      color: red;
    }
    ```

## 06-3. CSS 기본 선택자

- 선택자는 웹 문서에서 어느 부분에 스타일을 적용할지 알려 주는 것
- 미리 약속되어 있음

### 전체 선택자

- 모든 요소에 적용할 때 사용

```css
*{속성: 값; ...}
```

```css
/* 전체 선택자 */
* {
  margin: 0;
  padding: 0;
}
```

### 타입 선택자 (태그 선택자)

- 특정 태그를 사용한 모든 요소에 스타일 적용
- 브라우저 기본 스타일을 사용자 스타일로 덮어 쓸 때

```css
/* 타입 선택자 */
h3 {
  font-size: 36px;
  color: red;
}
```

### **클래스 선택자**

- 클래스 명으로 요소 선택, 다른 선택자와 구별
- 앞에 '.'반드시 붙여야함

```css
/* 클래스 선택자 */
.sect-1 {
  background-color: antiquewhite;
}
.sect-2 {
  background-color: aqua;
}
.sect-3 {
  background-color: blueviolet;
}
.sect-4 {
  background-color: yellowgreen;
}
```

### **id 선택자**

- id는 중복 사용할 수 없음 한 번만 사용하는 고유한 값
- 요소를 id명으로 선택하기

```css
#아이디명 {
  속성1: 속성1 값;
  속성2: 속성2 값;
}
```

```html
<div id="container"></div>
```

```css
#container {
  width: 500px;
  height: 500px;
  padding: 20px;
  margin: 20px auto;
  border: 2px solid #000;
}
```

### 그룹 선택자

- 여러개 요소를 선택
- 같은 스타일 규칙을 사용

```css
선택자1, 선택자2, 선택자3, ... {스타일 규칙}
```

## 06-4. 스타일 시트

### Cascading 의미

- 스타일 시트에서는 우선순위가 위에서 아래, 즉 계단식으로 적용된다는 의미
- CSS에서는 웹 요소에 둘 이상의 스타일을 적용할 때 우선수누이에 따라 적용할 스타일을 결정
- 스타일 우선순위
  - 스타일 규칙 중요도와 적용 범위에 따라 우선순위 결정
  - 그 우선순위에 따라 위에서 아래로 스타일 적용
- 스타일 상속
  - 태그의 포함 관계에 따라 부모 요소의 스타일을 자식 요소로
  - 위에서 아래로 전달

### 스타일 우선순위

- 중요도
  - 사용자 스타일 > 제작자 스타일 > 브라우저 기본 스타일

- 적용범위
  - !important > 인라인 스타일 > id 스타일 > 클래스 스타일 > 타입 스타일

- 작성 순서
  - 나중에 작성한 스타일이 먼저 작성한 스타일을 덮어씀

### 스타일 상속

- 자식 요소에 별도로 스타일을 지정하지 않으면 부모 요소의 스타일 속성들이 자식 요소로 전달

# 07. 텍스트 스타일

## 07-1. 폰트(글꼴) 속성

- 글자의 모양

### font-family

- 글꼴 지정
- 기본형

```
font-family: 글꼴이름 | 글꼴이름, 글꼴이름, ...;
```

### font-size

```
font-size: 절대크기 | 상대크기 | 크기 | 백분율
```

- 절대크기: 브라우저에서 지정한 글자 크기
- 상대크기: 부모 요소의 글자 크기를 기준으로 상대적인 글자 크기 지정
- 크기: 브라우저와 상관없이 글자 크기를 직접 지정
- 백분율: 부모 요소의 글자 크기를 기준으로 백분율(%) 표시

- 단위
  - em: 부모 요소에서 지정한 글꼴의 크기를 기준으로 몇배?
  - rem: 문서 최상단(root)에서 지정한 크기를 기준으로 몇배?
  - px: 모니터의 1픽셀을 기준으로 1px
  - 그외 ex,pt

### font-weight

- 글자 굵기
- normal, bold, bolder, lighter
- 100, 200, 300, ..., 900

```
font-weight: 굵기;
```

## 07-2. 웹 폰트 사용

### 웹 폰트 업로드 및 사용

- 설치용 .ttf, .otf
- woff, woff2, eot

```css
@font-face {
  font-family: 폰트 이름;
  src: url("폰트 파일 경로");
}
```

```css
@font-face {
  font-family: "Mrs Saint Delafield";
  src: url("../assets/fonts/MrsSaintDelafield-Regular.ttf");
}

h1 {
  font-family: "Mrs Saint Delafield", cursive;
  font-weight: 400;
  font-style: normal;
  font-size: 48px;
}
```

## 07-3. 텍스트 관련 스타일 속성

### color

```css
선택자 {
  color: 색상;
}
```

- 16진수 Hex: #ff6600, #f60, #df2727
- rgb, rgba: rgb(216, 38, 38), rgba(0, 0, 0, 0.5)
- hsl, hsla: hsl(140, 69%, 54%), hsla(0, 100%, 50%, 0.80)

### text-align

- 텍스트 정렬
- start: 현재 텍스트 줄의 시작 위치에 맞춰 문단 정렬
- end: 현재 텍스트 줄의 끝 위치에 맞춰 문단 정렬
- left: 왼쪽 정렬
- right: 오른쪽 정렬
- **center**: 가운데 정렬
- justify: 양쪽 정렬
- match-parent: 부모 요소를 따라 문단을 정렬

### line-height

- 행간(줄 간격)
- px, 백분율, %

### text-decoration

- underline(밑줄), line-throgh(취소선), overline(윗줄), none(없음)

### text-shadow

- text-shadow: X축 Y축 Blur값 색상값(hex, rgb, rgba, hsl, hsla)

### text-transform

- 영문자 표기할 때 대소 문자를 원하는대로 변경
- none: 기본값
- capitalize: 첫 번째 글자를 대문자로 변환
- uppercase: 모든 글자 대문자 변환
- lowercase: 모든 글자 소문자 변환
- full-width: 가능한 한 모든 문자를 전각 문자로 변환

```css
선택자 {
  text-transform: uppercase;
}
```

### letter-spacing, word-spacing

- lette-spacing: 자간(글자 사이의 간격)
- word-spacing: 단어와 단어 사이 간격 (잘 안씀)

## 07-4. 목록 스타일

### list-style-type

- bullet 모양, 번호 스타일 지정
  - disc: • 채운 원 모양
  - circle: 빈 원 모양
  - sqaure: 채운 사각형
  - decimal: 1, 2, 3, 4, ...
  - decimal-leading-zero: 01, 02, 03, 04, ...
  - lower-roman: ⅰ, ⅱ, ⅲ, ⅳ, ...
  - upper-roman: Ⅰ, Ⅱ, Ⅲ, Ⅳ, ...
  - lower-alpha 또는 lower-latin: a, b, c, d, ...
  - upper-alpha 또는 upper-latin: A, B, C, D, ...
  - none: 없음

### list-style-image

- 불릿을 원하는 이미지로

```css
ul {
  list-style-image: url("이미지 경로");
}
```

### list-style-position

- 불릿이나 번호의 위치를 들여 쓰기

```
list-style-position: inside(들여쓰기) | ouside(기본값);
```

### list-style

- list-style-type, image, position 한꺼번에 표시

```css
ul {
  /* list-style: lower-alpha inside; */
  list-style: none;
}
```

## 07-5. 표 스타일

- 개인적으로 알아보실 분만 알아보기

# 08. **레이아웃과 CSS 박스모델**

- 웹 문서에서 내용을 배치할 때는 각 요소를 박스 형태로 구성
- 이것을 CSS 박스 모델이라고 함
- 여백(margin), 안쪽여백(padding), 테두리(border), 콘텐츠 영역으로 구성

## 08-1. 박스 모델

### 블록 레벨 요소와 인라인 레벨 요소

- 블록 레벨인지 인라인 레벨 요소인지에 따라 요소를 나열하는 방법이 달라진다.
- 블록 레벨 요소: 혼자 한 줄을 다 차지, 너비가 100%
  - div, h1, p, 등

- 인라인 레벨 요소: 한 줄을 다 차지하지 않고, 콘텐츠만큼만 영역 차지
  - span, img, strong, a, 등

### 콘텐츠 영역, padding, border, margin

### width, height

- 너비, 높이
- 크기: px, em, rem 단위로 지정
- 백분율: 부모 요소를 기준으로 %지정
- auto: 콘텐츠 양에 따라 자동으로 결정, 기본값

### box-sizing

- border-box: 테두리를 포함한 너비, 높이
- content-box: 테두리를 포함하지 않은 콘텐츠 영역 만큼만, 기본값

### box-shadow

- X축: 수평거리, 왼쪽은 -, 오른쪽은 +
- Y축: 수직거리, 위쪽은 -, 아래쪽은 +
- 흐림정도: 값이 커질 수록 부드러운 그림자 표시
- 퍼짐정도: 그림자 크기
- 색상: 기본값은 검정색
- inset: inner shadow 안쪽 그림자로 표시

```css
.btn {
  margin: 0 auto;
  width: fit-content;
  font-size: 24px;
  padding: 8px 24px;
  border: 1px solid #000;
  border-radius: 99px;
  box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
  /* box-shadow: inset 2px 2px 4px rgba(0, 0, 0, 0.2); */
}
```

## 08-2. 테두리 스타일

### 박스 모델의 방향

- 4개의 방향: top -> right -> bottom -> left
- 3개의 방향: top -> left/right -> bottom
- 2개의 방향: top/bottom -> left/right
- 1개: top/left/bottom/right

### border-style

- none(기본값)
- hidden: 테두리 숨기기
- **solid**: 실선
- dotted: 점선
- dashed: 짧은 직선
- double: 이중선
- groove: 홈이 파인 듯 입체 느낌
- inset
- outset
- ridge

### border-width

- 테두리 두께

### border-color

- 테두리 색상

### border

- 테두리 스타일을 묶어 지정

```css
.box {
  width: 500px;
  height: 500px;
  margin: 50px auto;
  border-style: solid;
  border-width: 8px 24px 16px 32px;
  border-color: rgba(255, 30, 30, 0.678);

  border: 4px solid rgba(255, 30, 30, 0.678);
}
```

### border-radius

- 모서리 둥글게, 테두리 둥글게
- 크기, 백분율(만약 값이 50%: 정사각형일때->정원, 직사각형일때->타원)
- 방향 top/left -> top/right -> bottom/right -> bottom/left

```css
.box {
  width: 500px;
  height: 500px;
  margin: 50px auto;
  /* border-style: solid; */
  /* border-color: rgba(255, 30, 30, 0.678); */
  /* border-width: 8px 24px 16px 32px; */
  border: 4px solid rgba(255, 30, 30, 0.9);
  /* border-radius: 50%; */
  border-radius: 50px;
  border-top-left-radius: 400px;
}
```

## 08-3. 여백

- 4개의 방향: top -> right -> bottom -> left
- 3개의 방향: top -> left/right -> bottom
- 2개의 방향: top/bottom -> left/right
- 1개: top/left/bottom/right

### margin

- 요소 주변의 여백을 설정
- px, rem, em, %, auto

```
/* 상하 여백 50px, 좌우 여백 자동 -> 요소가 가운데 */
margin: 50px auto;
```

### margin 중첩 현상

- 세로로 배치할 경우 각 요소의 마진과 마진이 서로 만나면
- 큰 쪽으로 겹쳐지는 문제

```css
.box-1 {
  width: 300px;
  height: 300px;
  border: 4px solid #000;
  margin: 50px auto;
}
.box-2 {
  width: 300px;
  height: 300px;
  border: 4px solid #000;
  margin: 30px auto;
}
```

### padding

- 안쪽 여백
- 콘텐츠와 박스 사이 여백

```css
.box-1 {
  width: 300px;
  height: 300px;
  border: 4px solid #000;
  margin: 50px auto;
  padding: 16px;
}
.box-2 {
  width: 300px;
  height: 300px;
  border: 4px solid #000;
  margin: 30px auto;
  padding: 32px;
}
```

## 08-4. 레이아웃 만들기

### display

- block: 블록 레벨 요소로 만든다.
- inline: 인라인 레벨 요소로 만든다.
- inline-block: 인라인 레벨 요소와 블록 레벨 요소의 속성을 모두 가지고 있음
- none: 화면에 표시 하지 않음
- **flex: flex 박스**

```css
ul,
li {
  list-style: none;
}

ul {
  margin: 20px auto;
  padding: 16px;
  border: 1px solid #000;
}

li {
  display: inline-block;
  border: 1px solid #000;
  padding: 8px;
  margin: 16px;
}
```

### float

- 요소를 문서 위에 떠 있게 만든다.
  - left: 해당 요소를 문서의 왼쪽에 배치
  - right: 해당 요소를 문서의 오른쪽에 배치
  - none: 기본값

### float 속성 해제 clear

- float 속성이 더 이상 유효하지 않다고 알려줌
  - left: float: left를 해제
  - right: float: right를 해제
  - both: left, right 둘다 해제

```css
img {
  float: left;
  margin-right: 40px;
  width: 800px;
  height: 800px;
}

p {
  margin-top: 16px;
}
.bottom-text {
  clear: both;
}
```

```css
div {
  width: 100px;
  height: 100px;
}

.box-1 {
  background-color: aqua;
  float: left;
  margin-top: 20px;
  margin-right: 20px;
}
.box-2 {
  background-color: yellowgreen;
  float: left;
  margin-top: 20px;
}
.box-3 {
  background-color: violet;
  width: 100%;
  margin-top: 20px;
}
.box-4 {
  background-color: burlywood;
  clear: both;
  margin-top: 32px;
  width: 100%;
}
```

### **flex**

#### 용어 정리

- flex container (부모 박스) : 플렉스 박스 레이아웃을 적용할 flex item을 묶는 요소
- flex item (자식 박스)
- main axis (주축)
- cross axis (교차축)

#### flex item(자식 박스)을 배치 하는 flex container(부모 박스)의 속성

- **justify-content: 주축의 정렬 방법**
- **align-items: 교차축의 정렬 방법**
- align-self: 교차축에 있는 개별 flex item의 정렬 방법
- align-content: 교차축에서 여러 줄로 표시된 항목의 정렬 방법

- _display 속성_
  - **flex**: 컨테이너가 block처럼 동작 (새 줄에서 시작, 부모 너비를 100% 채움)
  - inline-flex: 컨테이너가 inline-block처럼 동작 (옆으로 나란히 배치, 내용만큼만 너비 차지)

- _플렉스 주축과 방향을 지정하는 flex-direction_
  - row (기본값)
  - row-reverse
  - column
  - colume-reverse

- _flex item의 줄을 바꾸는 flex-wrap_
  - nowrap (기본값)
  - wrap
  - wrap-reverse

- _주축 정렬 방법 justify-content_
  - flex-start: 주축의 시작점
  - flex-end: 주축의 끝점
  - center: 주축의 중앙
  - space-between: 첫 번째 항목과 끝 항목을 주축의 시작점과 끝점에 배치 후 나머지는 그 사이에 균등하게 배치
  - space-around: 모든 항목을 주축에 균등하게 배치

- _교차축 정렬 방법 align-items_
  - flex-start: 교차축 시작점
  - flex-end: 교차축 끝점
  - center: 교차축 중앙
  - baseline: 교차축의 문자 기준선에 맞춰 배치
  - stretch: flex item을 늘려 교차축에 가득 차게 배치

- _여러 줄일 때 교차축 정렬 방법 align-content_
  - flex-start
  - flex-end
  - center
  - space-between
  - space-around
  - stretch

#### flex item(자식 박스)의 속성

- _align-self_
  - 특정 항목만 지정
  - flex-start
  - flex-end
  - center
  - stretch

## 08-5. 웹 요소 위치 지정 position

# 09. 이미지, 그라데이션, 배경

# 10. CSS 고급 선택자

# 11. 트랜지션, 애니메이션

# 12. 반응형, 미디어 쿼리
