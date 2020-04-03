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

CSS

Cascading Style Sheets

각 요소들이 어떻게 생겨야하는지 브라우저에게 알려주는 언어. 색깔, 모양, 크기 등

HTML = 마킹
CSS = 디자인