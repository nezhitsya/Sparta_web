[수업 목표]

1. HTML, CSS 기초 지식 이해
2. 모바일 대응 가능한 페이지 완성

## 01. 배울 것

- 서버 / 클라이언트 / 웹 동작 개념
  - 웹 페이지는 모두 서버에서 `받아서 -> 그려주는` 것
  - 브라우저는 요청을 보내고 받은 HTML 파일을 그려주는 일 수행
- HTML (뼈대) CSS (꾸미기) Javascript (움직이기)

## 02. 준비하기

[Visual Studio Code (VS Code)](https://code.visualstudio.com/download)

## 03. HTML

- HTML은 크게 head와 body로 구성
  - head : 페이지의 속성 정보 (meta, script, link, title)
  - body : 페이지의 내용

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>스파르타코딩클럽 | HTML 기초</title>
  </head>

  <body>
    <!-- 구역을 나누는 태그들 -->
    <div>나는 구역을 나누죠</div>
    <p>나는 문단이에요</p>
    <ul>
      <li>bullet point!1</li>
      <li>bullet point!2</li>
    </ul>

    <!-- 구역 내 콘텐츠 태그들 -->
    <h1>
      h1은 제목을 나타내는 태그입니다. 페이지마다 하나씩 꼭 써주는 게 좋아요.
      그래야 구글 검색이 잘 되거든요.
    </h1>
    <h2>h2는 소제목입니다.</h2>
    <h3>h3~h6도 각자의 역할이 있죠. 비중은 작지만..</h3>
    <hr />
    a 태그입니다: <a href="http://google.com/" target="_blank">하이퍼링크</a>
    <hr />
    img 태그입니다:
    <img
      src="https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png"
    />
    <hr />
    input 태그입니다: <input type="text" />
    <hr />
    button 태그입니다: <button>버튼입니다</button>
    <hr />
    textarea 태그입니다: <textarea></textarea>
  </body>
</html>
```

> 정렬 (mac - cmd + k + f / window - ctrl + k + f)

## 04. CSS

> < head > ~ </ head > 안에 < style > ~ </ style > 로 공간을 만들어 작성

1. 태그를 바로 가리켜서 꾸며주기

```javascript
h1 {
	color: red;
}
```

2. 이름표를 붙이고 꾸며주기

```javascript
.test {
    color: green;
    font-size: 50px;
}
```

> 실행 (mac - option + b / window - alt + b)

## 04. CSS 응용

1. div로 구역을 나눈다.

```html
<div class="box">
  <div>첫 번째 구역</div>
  <div>두 번째 구역</div>
</div>
```

2. 구역에 사이즈를 주고 색을 치한다.

```css
.box {
  background-color: green;
  width: 800px;
  height: 800px;
  color: white;
}

.first {
  background-color: red;
  width: 300px;
  height: 300px;
}

.second {
  background-color: blue;
  width: 400px;
  height: 400px;
}
```

- 배치 변경 `display: flex` & 간격 `margin`

```css
.box {
  background-color: green;
  color: white;

  width: 800px;
  height: 800px;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.first {
  background-color: red;

  width: 300px;
  height: 300px;

  margin-bottom: 20px;
}

.second {
  background-color: blue;
  width: 400px;
  height: 400px;
}
```

## 06. 계획 세우기

<p align="center">
  <img width="900" src="https://user-images.githubusercontent.com/60697742/152297859-6183ac46-e5d9-4633-be74-63d8629fa413.png">
</p>

1. 배경
2. 위에 타이틀
3. 밑으로 아이템 배치
4. 플로팅 버튼

**배경 div 생성**

1. index.html 파일 생성
2. < title > </ title >
3. 배경이 될 div 생성

```javascript
.background {
    background-color: green;
    width: 400px;
    height: 800px;
}

<div class="background"></div>
```

## 07. 그림 배경

- 배경 이미지 화면에 꽉 차게 설정 (가로 길이 최대치 설정)

```css
.background {
  background-color: green;
  width: 100vw;
  height: 100vh;
  max-width: 450px;

  background-image: url("https://2022-01-newyear.s3.ap-northeast-2.amazonaws.com/bg_default.png");
  background-position: center;
  background-size: cover;

  margin: auto;
}
```

- body 여백 제거

```css
body,
h1,
p {
  margin: 0;
  padding: 0;
}
```

## 08. 제목 구성

- 큰 div로 작은 제목 2개 위치
  - div, h1, p, span 태그 사용
  - 가운데 정렬 `display: flex`

```javascript
<div class="background">
  <div class="title">
    <h1>덕담 하나 주면 안 잡아먹지!</h1>
    <p>
      다영 님이 받은 덕담 : <span>2개</span>
    </p>
  </div>
</div>
```

- 디자인

```css
.title {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  padding-top: 5vh;

  color: #3f3732;
}

.title > h1 {
  font-size: 22px;
  background-color: white;

  padding: 8px 16px;
  border-radius: 16px;

  margin-bottom: 16px;
}

.title > p {
  font-size: 18px;
}

.title > p > span {
  font-size: 22px;
}
```

## 09. 폰트 적용

- 폰트 import

```css
@font-face {
  font-family: "Cafe24Ssurround";
  src: url("https://2022-01-newyear.s3.ap-northeast-2.amazonaws.com/Cafe24Ssurround.woff")
    format("woff");
}

* {
  font-family: "Cafe24Ssurround";
}
```

## 10. 버튼 생성

- 커서 모양 변경

```css
.btn {
  width: 300px;
  height: 50px;
  background-color: #3f3732;

  color: white;

  font-size: 18px;
  border-radius: 10px;

  cursor: pointer;
}
```

- 글씨 가운데

```css
.btn {
  width: 300px;
  height: 50px;
  background-color: #3f3732;

  color: white;

  font-size: 18px;
  border-radius: 10px;

  cursor: pointer;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
```

- 버튼 떠다니게 설정

```css
.btn {
  width: 300px;
  height: 50px;
  background-color: #3f3732;

  color: white;

  font-size: 18px;
  border-radius: 10px;

  cursor: pointer;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  position: fixed;
  bottom: 16px;
  left: calc(50% - 150px);
}
```

## 11. 아이콘 삽입

- 서버에서 데이터를 받아 자동으로 아이콘 삽입

```javascript
.box > img {
    width: 70px;
}
...
<div class="box">
    <img src="https://2022-01-newyear.s3.ap-northeast-2.amazonaws.com/object3.png">
</div>
```

- 아이콘 원하는 곳에 배치

```css
.box > img {
  width: 70px;

  position: absolute;
  left: 50%;
  bottom: 50%;
}
```

- 아이콘에 alert 삽입

```javascript
<img
  onclick="alert('새해복!')"
  src="https://2022-01-newyear.s3.ap-northeast-2.amazonaws.com/object3.png"
/>
```

<p align="center">
  <img width="856" src="https://user-images.githubusercontent.com/60697742/152305489-afa7400c-d718-4fa9-9546-64629f9ebce0.png">
</p>

## 12. JS 삽입

- JS 역할

1. 덕담 기록하기
2. 덕담 불러와 아이콘 삽입

```javascript
<script src=" "></script>
<script>
    let mycode = ' ';
</script>
```

## 13. 공유하기

<p align="center">
  <img width="500" src="https://user-images.githubusercontent.com/60697742/152306131-abac4842-43a4-48b5-824b-eb294ce18775.png">
</p>

**og 태그**

```javascript
<meta property="og:title" content="ㅇㅇ 님의 덕담 페이지"/>
<meta property="og:description" content="덕담 한마디 남겨주세요!"/>
<meta property="og:image" content="https://2022-01-newyear.s3.ap-northeast-2.amazonaws.com/ogimage.png"/>
```

- `og:image` `og:title` `og:description` 을 미리 세팅해두면 공유 시 원하는 형태로 보여짐

## 14. 배포하기

[결과 보러가기](https://deokdam.spartacodingclub.kr/CpDrMTrQot74/index.html)
