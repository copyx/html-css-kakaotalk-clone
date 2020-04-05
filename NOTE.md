## HTML(HyperText Mark-up Language)

하이퍼텍스트 **마크업** 랭귀지

여기서 마크업이 중요함.
마크업이란 표시하는 것을 의미.
**브라우저에게 "여기서부터 여기까지가 타이틀이야"라고 표시해서 각 요소들이 무엇인지 알려준다고 생각하면 쉬움.**

태그(Tag)로 구성되어있음.

### 태그의 형태

#### 일반적으로 쌍을 이루는 태그

```html
<name attribute="value">Content</name>
```

#### Self-contained 태그

스스로 열고 닫는 태그라는 의미.
이 태그는 그 자체로 정보를 제공하기 때문에 쌍으로 감쌀 필요가 없음.

```html
<!DOCTYPE html> 
```

#### Semantic 태그 VS Non-semantic 태그

태그에 의미가 있는가의 차이.

```html
<!-- Semantic -->
<h1>Big title</h1>
<header>It is header</header>
<section>This is difficult section.</section>

<!-- Non-semantic -->
<div>박스, 컨테이너 역할을 많이하마.</div>
<span>텍스트를 위한 컨테이너</span>
```

#### ID and Class

- ID: 요소별로 하나만 가질 수 있고, 고유한 아이디임.
- Class: 여러개를 가질 수 있고, 여러 요소가 같은 클래스를 가질 수 있음.

### HTML 문서 구성

```html
<!DOCTYPE html>
<html>
    <head>
    </head>
    <body>
    </body>
</html>
```

#### `<head>`

유저에게 보이지 않는 브라우저에게 필요한 정보를 제공. Information

#### `<body>`

유저에게 보이는 정보. Contents
---

## CSS(Cascading Style Sheets)

각 요소들이 어떻게 생겨야하는지 브라우저에게 알려주는 역할. (색깔, 모양, 크기 등)

HTML = 마킹 | CSS = 디자인

### CSS 작성법

```css
selector{
    property: value;
}

h1{
    background-color: #112233;
}
```

#### 선택자(Selector)

스타일을 적용할 대상을 지정하는 요소. 주로 세 가지를 이용함.

- Tag : `tag{}`
- Class : `.class{}`
- ID : `#id{}`

위 세 가지를 복합해서 사용할 수 있으며, 이 외에도 자식, 인접 등 다양한 선택자들이 있음.

[CSS Selectors Reference](https://www.w3schools.com/cssref/css_selectors.asp)

### CSS 적용 방법

HTML 파일 내에 작성하는 방법과 HTML 파일 외부에 작성하고 이를 연결하는 방식이 있음.

#### HTML 파일 내 작성

`<head>` 태그 안에 `<style>` 태그로 CSS 선언 가능. 해당 페이지에 적용됨. 다만, HTML 문서마다 모두 따로 관리해야하는 불편함이 있음.

#### HTML 파일 밖에 작성(feat styles.css)

`styles.css` 처럼 `css` 확장자로 파일을 만들고 그 안에 CSS 선언. 이 파일은 HTML 문서의 헤더에서 `<link>` 태그로 연결 가능.

```html
<head>
    <link href="styles.css" rel="stylesheet">
</head>
```

파일을 분리해서 관리하기 때문에 페이지마다 관리할 필요가 없어서 편함.

### Box Model

많은 요소들이 박스 모델로 되어있음.

```
Content | Padding | Border | Margin
```

어떤 요소를 만들면 사각형 Box 모양으로 공간을 차지하게됨. 이 박스의 테두리가 Border, 테두리 안쪽 간격을 Padding, 테두리 바깥쪽 간격을 Margin 이라고 함.

#### Padding, Margin 설정 방법

```css
.box{
    /* 방향별로 각각 적용 */
    padding-top: 50px;
    padding-left: 50px;
    margin-top: 50px;
    margin-left: 50px;
    /* 모든 방향 한꺼번에 적용 */
    padding: 50px; 
    /* 한 프로퍼티에서 방향별로 각각 적용. 상하좌우 순서. */
    padding: 20px 0px 50px 30px;
    margin: 50px 20px 30px 40px;
}
```

#### Border 설정 방법

```css
.inside-box{
    /* 보더 속성별로 설정 */
    border-width: 5px;
    border-color: red;
    border-style: dashed;
    /* 한 프로퍼티에서 한 꺼번에 설정 */
    border: 5px dashed red;
}
```

### Display

```css
.class{
    display: block;
}
```

#### Block

요소의 옆에 아무 것도 허용하지 않음. 요소의 크기와 상관없음. 디폴트 설정. 폭, 높이가 존재함.

#### Inline-block

요소들을 같은 라인에 둘 수 있음. 폭, 높이가 존재함.

#### Inline

블록이나 박스가 아닌 텍스트처럼 적용이됨. 요소의 컨텐츠 크기만큼만 적용됨. 블록처럼 따로 크기를 설정할 수 없음.

### Position

```css
#id{
    position: fixed;
}
```

#### Static

기본적인 포지션 말 그대로 정적인 포지션으로 페이지 내 정해진 위치에 고정. 스크롤하면 스크롤하는대로 올라감.

#### Fixed

페이지가 아닌 스크린에 고정되는 포지션. 스크롤해도 화면의 해당 위치에 고정되서 따라옴.

#### Relative

Absolute 포지션의 기준이 되는 포지션. 단, Absolute 포지션이 설정된 태그의 부모이거나 조상이어야만 기준으로 역할함.

#### Absolute

Relative 포지션을 기준으로 위치하는 포지션. 부모나 조상 중 Relative 포지션이 없으면 body 태그를 기준으로 위치함.

### Flexbox

인라인블록을 이용하던 과거에는 문제가 많았음. 공간에 맞춰 마진을 하나하나 조정해야했고, 화면 크기가 변하는 것에 모두 수동으로 대응해야했음. 자동 조정되는 그리드가 없었음. 이를 해결해주는 것이 Flex!

플렉스가 설정된 요소의 자식 요소들이나 컨텐츠의 간격, 방향, 정렬 등의 적용이 가능.

```css
.father{
    display: flex;
}
```

Flex는 **진행축(main axis)과 교차축(cross axis) 개념**이 있음. 진행축은 아이템들이 배치되는 방향, 교차축은 진행축과 90도 교차하는 방향을 축을 이야기함. 단순히 X축, Y축으로 이야기하지 않는 이유는 축의 방향도 바꿀 수 있기 때문임.

#### `justify-content`

진행축의 배치 방법을 결정하는 프로퍼티.

#### `align-items`

교차축의 배치 방법을 결정하는 프로퍼티.

#### `flex-direction`

플렉스의 방향을 결정하는 프로퍼티

#### `flex-wrap`

아이템의 줄바꿈 여부와 방향을 설정하는 프로퍼티

#### `flex-flow`

`flex-direction`과 `flex-wrap`을 동시에 설정할 수 있는 프로퍼티

#### `align-content`

플렉스 아이템들이 여러 줄일 때 줄간의 간격이나 정렬을 결정하는 프로퍼티

#### `align-self`

여러 아이템 중 원하는 단일 플렉스 아이템에 교차축 배치 방법을 설정하는 프로퍼티

#### `order`

아이템의 순서를 설정하는 프로퍼티. 기본 0. 양수, 음수 모두 설정 가능.

[Flexbox 공부용 코드게임 - 이거 좋음!](http://flexboxfroggy.com/)

### Selectors and Psuedo Selectors

#### 속성 선택자(Attribute Selector)

HTML 요소들의 속성을 이용해 선택.

- `a[attribute]{}` : 속성이 있으면 모두 선택
- `a[attribute="value"]{}` : 속성값이 문자열이면 선택
- `a[attribute~="value"]` : 속성값이 문자열을 포함하면 선택(스페이스로 구분된 단어 기준)
- `a[attribute|="value"]` : 속성값이 문자열로 시작하면 선택(단어 전체이거나 하이픈(-)으로 구분)
- `a[attribute^="value"]` : 속성값이 문자열로 시작하면 선택
- `a[attribute$="value"]` : 속성값이 문자열로 끝나면 선택
- `a[attribute*="value"]` : 속성값이 문자열을 포함하면 선택

#### 결합자(Combinators)

선택자 간의 관계를 설명하는 것

##### 자손 선택자(Descendant Selector)

명시된 요소의 자손(직계 자식이 아닌 몇 단계를 거치든)인 모든 요소를 선택.

```css
div p {
    background-color: green;
}
```

##### 자식 선택자(Child Selector)

명시된 요소의 직계 자식인 모든 요소를 선택.

```css
div > p {
    background-color: green;
}
```

##### 인접 자매 선택자(Adjacent Sibling Selector)

명시된 요소와 같은 부모를 갖고, 바로 다음에 따라오는 요소를 선택.

```css
div + p {
    background-color: green;
}
```

##### 일반 자매 선택자(General Sibling Selector)

명시된 요소와 같은 부모를 갖는 요소를 선택


```css
div ~ p {
    background-color: green;
}
```

#### Pseudo Classes

요소의 특별한 상태를 정의하는데 사용

> 예시)
> 요소에 마우스 오버된 상태
> 형제 요소들 중 마지막일 때
> 현재 요소에 포커스가 잡혔을 때 등

#### Pseudo Elements

요소의 특정한 일부분에 스타일을 적용할 때 사용

> 예시)
> 요소의 첫 글자, 첫 줄
> 요소의 컨텐츠 전, 후 등

### Transitions

요소의 상태 변화 시 두 상태간의 전환을 정의하는 것.

```css
.box {
    transition: target duration timing-function delay;
}
```

[transition property - MDN](https://developer.mozilla.org/ko/docs/Web/CSS/transition)

### Transformations

요소 모양이나 크기, 방향 등 좌표공간을 변환하는 효과.

```css
.box {
    transform: 
}
```

[transform property - MDN](https://developer.mozilla.org/ko/docs/Web/CSS/transform)

## 기타 궁금증

HTML과 CSS는 언어인가?