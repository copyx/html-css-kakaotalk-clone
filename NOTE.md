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

## 기타 궁금증

HTML과 CSS는 언어인가?