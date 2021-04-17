# 최신 표준 HTML5+CSS3 디자인

> **왜 배우나요?**
> 최근에 리액트 + Redux로 프로젝트를 진행하면서 느꼈던점이 있다.
> 너무 js에만 집착하다 보니 웹에 기초가 되는 HTML, 그리고 CSS를 너무 대충하지 않았나...
> 하는 생각을 하게 되었는데 그때에 나를 반성하고자, 그리고 변해보고자 이 [**최신 표준 HTML5+CSS3 디자인**] 를 읽어보면서 기초를 탄탄히 다지는 시간이 되었으면 좋겠다.

_틀린 내용이나 오타가 있으면 PR을 날려주세요! 적극 검토하겠습니다!_

## 결과물

[링크](https://hong-junhyeok.github.io/HTML5-CSS3_Design/Web/index.html)

## 목차

- [사전 준비](#사전-준비)
- [최상위 페이지 만들기](#최상위-페이지-만들기)
- [콘텐츠 페이지 만들기](#콘텐츠-페이지-만들기)
- [기사 목록 페이지 만들기](#기사-목록-페이지-만들기)
- [디자인 재구성](#디자인-재구성)
- [번외-HTML,CSS뿌수기](#HTML-CSS-뿌수기)

## 사전 준비

### **시멘틱 태그란?**

의미가 있는 태그라는 의미로, SNS에서 웹페이지를 공유할 때 페이지의 제목, 썸네일 그림이 적합하게 들어가는 것도 시멘틱 태그 덕분이다.

### **페이지를 만드는 순서와 구조**

페이지를 만들때에는 **최상위 페이지**부터 만든다.
최상위 페이지에서는 헤더와 푸터 사이에 콘텐츠를 넣어서 완성한다.

그 다음 **콘텐츠 페이지**에는 헤더와 푸터를 남겨두고 안쪽의 내용을 중점적으로 작업한다.

콘텐츠 페이지를 작업했으면 **소개 페이지/문의 페이지**를 작업한다.

### 페이지의 배색

페이지의 배색은 사이트의 인상을 결정하는 **중요한 요소**이다.
일단 메인 색상을 정해놓고, [Adobe Color CC](https://color.adobe.com/ko)라는 도구를 사용해서 한 가지 색을 기반으로 어울리는 색을 찾는다.

### 웹 페이지 준비하기

웹 페이지 만들 때는 화면에 출력할 내용을 HTML파일, 외관 디자인과 레이아웃 설정을 CSS에서 작성한다. 텍스트 에디터(VSCode)를 사용하거나 다른 에디터를 사용해도 무방하다.
**이떄 인코딩 설정은 UTF-8로 지정해준다.**

> #### 파일 저장 장소
>
> 파일을 저장할 Web폴더를 준비하고 HTML파일은 index.html, CSS파일은 style.css라는 이름으로 저장한다.

```html
<!--index.html-->
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <title>여기에 제목이 들어갑니다.</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    여기에는 내용이 들어갑니다.
  </body>
</html>
```

- `<!DOCTYPE html>` : 최신 HTML로 작성하겠다는 의미
- `<html lang="ko">` : html설정 전체를 마크업. lang속성으로 어떤 언어를 할지 명시
- `<meta charset="UTF-8">` : HTML파일의 인코딩 방식을 utf-8로 설정하겠다는 의미
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` : 스마트폰 , 태블릿과 같은 모바일 장치 전용 설정.

```css
/* CSS */
@charset "UTF-8";

/* 기본색 */
:root {
  --main-color: #123455;
  --accent-color: #123456;
  --dark-color: #000000;
}
```

- `@charset` : CSS파일의 인코딩 종류가 UTF-8이라는 것을 명시.
- `기본색 설정` : :root내부에 작성한 값들은 CSS상에서 사용할 일종의 변수같은 계념이다.
- `주석` : /\*\*/ 의 형태로 작성

## 최상위 페이지 만들기

- ## 히어로 이미지
  페이지에 아주 크게 표시되는 이미지 요소를 의미함.
  ![image](https://user-images.githubusercontent.com/48292190/114636634-6b434c00-9d02-11eb-934c-f870397f7e63.png)
  (헤더 이미지, 라지 헤더 등으로도 불림)

> **폰트 지정을 하지 않았을 때에 생길수 있는 문제**
> 환경(윈도우, Mac, Linux등 혹은 검색엔진)에 따라 폰트가 다 달라보일수 있는 문제가 있기때문에 통일감을 주기 위해서 폰트를 지정을 해줘야한다.

> **브라우저 너비에 따라 폰트 크기 변경하기**
> vw(화면 너비의 단위)라는 단위를 사용해서 각 장치의 화면 넓이마다 폰트의 크기를 다르게 보이게 할 수 있다.

> **큰 화면에서의 폰트 크기 조정하기**
> 사이트에서 폰트 크기가 너무 커지면 화면이 주는 압박감이 커지기 때문에 큰 화면에서는 폰트 크기를 고정시키는 작업을 하는 방법이 있다.
> 이때에는 media쿼리를 사용하면 되는데, 브레이크 포인트를 걸어서 화면의 너비가 몇일때, 스타일링을 다르게 줄 수 있다. 이를 **반응형 웹페이지**라고 한다.

### 글자의 간격을 주는 법.

`letter-spacing`이라는 속성을 써서 각 글자간의 간격을 줄 수 있다.

### 최소 높이를 확보하는 방법.

`min-height`라는 속성을 줘서 브라우저 창의 height가 min-height만큼 작아질 수 없게 **최소 높이를 확보하는 방법**이 있다.
최소 높이를 지정 함으로써 레이아웃이 깨지는 문제를 해결할 수 있다.

### 글자를 이미지 중앙에 배치하는 방법

`display : flex`로 flex레이아웃을 구성해준 다음에,
`justify-contents : center` , `align-items : center`를 주게 되면 요소가 가운데로 정렬되게 된다.

### 변수를 사용해서 글자 색 바꿔보기

`var(--color);`의 형식으로 변수를 사용할 수 있다.
하지만 변수 사용을 지원하지 않는 브라우저도 있기 때문에 color : #fff;이런식으로 두개 다 써주는게 베스트이다.

> **:root는 뭐하는 건가요?**
> :root를 사용하게되면 문서에 루트에 접근한다는 의미이다.
> 즉 html{} 과 같은 기능을 하는 것인데, 전역적으로 선언한 선택자라고 보면 될거같다.

### 반투명한 검정색 이미지를 중첩해서 어둡게 만들기

CSS는 포토샵이 아니기때문에 사진을 직접 수정할 순 없다. 그래서 반투명한 검은색 이미지를 겹쳐서 어둡게 만드는 효과는 낼 수 있다.
이때, 반투명한 색을 지정하는 방법은 `rgba()`라는 아이를 사용하면 된다. r은 붉은색 g는 초록색 b는 파란색 그리고 마지막 인자값은 투명도의 값을 조절한다.

> **그레이디언트란 무엇인가요?**
> 그레이디언트한 서서히 올라오는(내려가는) 느낌을 줄 수 있다.

```css
background-image: linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.5)),
  url(img/main_3.jpeg);
```

![image](https://user-images.githubusercontent.com/48292190/114655064-67292580-9d26-11eb-9c41-c7b23bd94f58.png)
`linear-gradient`라는 속성을 사용하면 사용 가능하다.

- ## 개요
  ![image](https://user-images.githubusercontent.com/48292190/114669311-b4b08d00-9d3c-11eb-867a-9d05fbae1a81.png)

## FontAwesome을 사용해서 아이콘 사용해보기

**FontAwesome**이라는 서비스는 손쉽게 다양한 아이콘들을 쓸 수있게 해주는 폰트 제공 서비스이다.

> **어떻게 FontAwesome을 사용하나요?**
> FontAwesome 웹사이트에 들어가셔서 절차에 따라서 이메일을 받고 그 이메일에서 받은 주소를 script src에 넣어주기만 하면 바로 FontAwesome을 사용할 준비가 된 것이다. (자세한 사항은 구글링...)

이때 ,아이콘은 **폰트**이기 때문에 크기를 조절할려면 폰트 크기를 조절해야 된다. `font-size`

### 미디어 쿼리를 사용하여 레이아웃 변경해보기

전 장에서 다루었던 미디어 쿼리를 사용해서 레이아웃을 변경할 수 있다.

```css
@media (min-width: 768px) {
  .conB .container {
    display: flex;
    max-width: var(--large-width);
    margin-left: auto;
    margin-right: auto;
  }

  .conB .text {
    flex: 1;
  }
}
```

768px이상으로으로 화면의 너비가 넓어지면 레이아웃을 flex로 바꿔주는 작업을 하는 것이다.

- ## 개요2
  ![image](https://user-images.githubusercontent.com/48292190/114686935-3361f600-9d4e-11eb-9588-496ca3aa5a40.png)

**flex레이아웃의 순서를 바꾸는 방법은?**
`flex-direction`이라는 것을 사용해서 `flex-direction: row-reverse;`를 하게되면
위와 같이 순서가 바뀐 모습을 볼 수 있다.

## -네비게이션

네이게이션은 **헤더와 푸터**이다.
흔히 네비게이션하면 ~아이나비~같은게 생각날수도 있는데 사실, 개념이 똑같다.
사용자가 옳바른 주소로 이동할 수 있도록 도와주는 컴포넌트이기 때문이다. 또한, 이 사이트의 정보같은거나 다양한 자료들이 들어갈 수 있다.

![image](https://user-images.githubusercontent.com/48292190/114714535-2bfe1500-9d6d-11eb-8b2d-88dd1274e8cb.png)

### 푸터 메뉴

푸터에 더 많은 기능을 부여하기 위해 푸터 메뉴를 추가할려고 한다.
이 푸터 메뉴도 당연히 반응형으로 디자인할려고 하며, `브레이크포인트는 (768px)`로 줄려고 한다.

**화면길이가 768px 이상일때**
![image](https://user-images.githubusercontent.com/48292190/114716604-2c97ab00-9d6f-11eb-95a2-0a6b5900720a.png)

**화면길이가 768px 미만일때**
![image](https://user-images.githubusercontent.com/48292190/114716645-36b9a980-9d6f-11eb-82b1-b20c48f760bb.png)

`flex`속성은 일종의 비율을 구현할 수 있게 해준다. 각 Div마다 flex : 1을 줘서 `1 : 1 : 1`을 구성하게 구현했다

> **저작권 표시하기**
> 보통 footer에 이 웹사이트에 대한 저작권을 표시하는데 일단 이 웹사이트 에서는 © Hong-JunHyeok. All rights reserved.이라고 명시하도록 하겠다.

### 푸터 레이아웃 설명

사이트의 정보(제목,폰 번호, 주소)와 링크 네비게이션,그리고 저작권 표시 문자 레이아웃을 어떻게 작성하는지 보도록 하자. 기본적으로 flex레이아웃이면 flex-wrap이라는 속성을 사용할 수 있는데, flex-wrap은 요소의 넓이가 100%가 넘어갈때, 자동으로 개행을 해주는 속성이다. 그렇기때문에 저작권 표시를 하는 **요소를 넓이 100%를 주게되면 자동으로 독단적인 라인을 가지는 레이아웃을 구성할 수 있게 만들어준다**.

그리고, 푸터를 구성할때에는 컨텐츠와 너비를 맞춰주는 작업을 해주는것이 좋다.
max-width의 속성을 --large-width의 값으로 설정을 해주었고,
`margin-right : auto` , `margin-left : auto`를 줌으로서 자동으로 가운데 정렬이 될 수 있도록 해주는 작업을 해준다.

## 헤더

이제 할 작업은 사이트의 가장 상단에 위치하는 **헤더**메뉴를 만들어볼려고 한다.
![image](https://user-images.githubusercontent.com/48292190/114796973-1a4c5a00-9dcd-11eb-9a5d-630b317ea625.png)

당연하게도 **반응형**으로 헤더를 만들어야 한다.
`flex`레이아웃을 사용해서 헤더를 만들었으며, 이번에 사용한 속성은
`justify-contents : space-between`이라는 것이다. 이 속성을 사용하게 되면 요소의 양 끝에 자동으로 정렬을 해주게 되는데(요소가 2개 있을때) header에서 max-width의 값을 --large-width를 줘서 최대값을 정해주고, `margin-right : auto` , `margin-left : auto`로 가운데로 정렬되게 해서 **콘텐츠와 헤더의 최대길이가 일치할 수 있도록** 설계했다.

### 토글되는 헤더를 만들어보자.

여기서 사용하는 것은 JS라는 아이다. 동적인 웹사이트를 만들려면 JS를 사용해서 구현해야 하는데, 여기서 우리가 사용할 라이브러리는 **제이쿼리**이다. 제이쿼리를 사용하면 많은 기능을 쉽게 구현할 수 있는데 한번 사용해보도록 하자.
![JQUERY](https://biketago.com/ufiles/story/13_m.jpg)

제이쿼리의 장점은 매우 **직관적인 코드**라는 것이다.
그만큼 개발자가 보기 편하고 개발하기 편하다. 하지만 제이쿼리의 **단점**이 있다면... **느리다. 느려도 너무 느리다.** 아무래도 많은 기능을 지원하다 보니 속도가 느려지는게 보인다.

> "jQuery를 사용할 때 getElementById보다 10배 느린 것을 볼 수 있습니다. querySelector보다는 다섯 배 느리고요. 이렇게 느린 속도가 조금씩 누적되다보면 상당한 차이를 야기할 수도 있습니다." <출처 : [제로초님 블로그](https://www.zerocho.com/category/jQuery/post/57b356d4d841141500b31e1e)>

또, 코드가 간결하기 때문에 쉽게 생각하는 사람들도 있겠지만...코드가 꼬이고 중복되는 경우가 많이 발생하기 때문에 **코드관리**가 어렵다.

**그렇기 때문에 요즘 개발자들은 제이쿼리 말고 다른 방법을 찾는것을 추천한다.**

이제 코드를 한번 보도록 하자.

```javascript
<script>
      $(function () {
        $(".headC").click(function () {
          $(".headB").slideToggle();
        });
      });
</script>
```

이렇게 하였을때 메뉴가 토글이 될것이다.

![gif](https://im7.ezgif.com/tmp/ezgif-7-3889679888aa.gif)

여기서 중요한 것은 **반응형 작업**이다.
왜냐하면 버튼을 큰 화면일때에는 없애야하기 때문이다.

headB에 있는 네비게이션들을 작은 화면일때 `display: none`을 해준다. 그런 다음에 토글 버튼이 클릭이 되었을때에,

```javascript
$(function () {
  $(".headC").click(function () {
    $(".headB").slideToggle();
  });
});
```

이부분 처럼 slideToggle이라는 함수를 실행시켜주면 JQuery에서 자동으로 `display : none`이 되었던 부분을 슬라이드 하는 애니메이션으로 변환시켜 주면서 화면에 보여지게 된다.

# 콘텐츠 페이지 만들기

### 페이지 디자인

하나의 사이트를 구성하는 페이지이므로 통일감 있게 디자인하는 것이 좋다.

## 콘텐츠 페이지

콘텐츠 페이지는 기사을 보여주는 것을 목적으로 하는 페이지이다.
콘텐츠 페이지의 구성 요소는 보통 **기사의 제목 , 문장 , 이미지, 빵 부스러기 리스트 등이 있다**

> **빵 부스러기 리스트란?**
> 서양 동화의 헨젤과 그레텔에서 다시 집으로 돌아가기 위해 빵을 조금씩 뜯어 놓아서 왔던 길을 기록하는 모습을 보고 나온 이름으로, 웹페이지에서 사용자가 방문한 페이지를 기록하는 리스트를 빵 부스러기 리스트라고 한다.

### 헤더가 제목과 겹치는 상황 발생

![image](https://user-images.githubusercontent.com/48292190/114801903-a2cff800-9dd7-11eb-84c2-a879e1ed333b.png)

위의 사진처럼 헤더가 콘텐츠와 겹치는 경우가 발생한다. 이는 `position : absolute;`라는 속성 때문인데, 일차적으로 해결하기 위해서는 absolute속성을 없애줘야 한다.

하지만 이렇게 되면 겹치는 문제는 없어지지만 최상위 페이지에서 문제가 생겨버리게 된다. 투명한 배경색이 사진과 겹치는 것을 유도했었는데, 최상위 페이지마저 겹치는 부분이 없어지게 되버렸다.

그래서 이를 해결할려면, hero이미지가 없을때에만 `position : absolute;`를 없애줘야 한다.
이를 한번 구현해보자.

먼저 contents.html의 body에 class로 nohero를 주고 아래의 css처럼 작성해주면 된다.

```css
header {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 100;
  width: 100%;
  background-color: rgba(255, 255, 255, 0.7);
}

.nohero header {
  position: static;
}
```

그리고 nohero 헤더 속성에 구분선을 줘서 콘텐츠와 거리를 주도록 해보겠다.

```css
/* 기본 색상 */
:root {
  --main-color: #5d9ab2;
  --accent-color: #bf6a7a;
  --dark-main-color: #2b5566;
  --text-bright-color: #fff;
  --icon-color: #fff;
  --icon-bk-color: #ddd;
  --large-width: 1000px;
  --purple-color: #a388f3;
  --gray-color: #ddd;
}

/* 생략 */

.nohero header {
  position: static;
  border-bottom: 1px solid var(--gray-color);
}
```

### 기사의 간격 설정하기

먼저 기사 주변의 여백 크기를 조정해보도록 하겠다.

```css
.post .container {
  padding: 30px 10px;
}
```

그런 다음에 max-width를 줘서 최대 길이를 주도록 하겠다.

```css
.post .container {
  padding: 30px 10px;
  max-width: var(--middle-width);
  margin-left: auto;
  margin-right: auto;
}
```

그러면 최종적으로 만들어지는 모습은 이렇다.
![image](https://user-images.githubusercontent.com/48292190/114802873-656c6a00-9dd9-11eb-8bb7-4dc75a4ad4f1.png)

### 기사의 디자인 지정하기

이제 우리가 할 작업은 각 디스플레이마다 폰트의 크기를 다르게 하는 작업이다.

- 스마트폰 => 14px
- 태블릿 => 16px
- PC => 18px

이런식으로 **기사의 폰트 크기**를 다르게 설정해볼려고 한다.
우리가 배워야 할 단위는 `rem`이라는 것인데, root요쇼의 폰트 크기에 대한 비율의 단위이다.

> 2rem은 root폰트 크기 x 2가 되는것이다.

```css
@media (max-width: 599px) {
  :root {
    font-size: 14px;
  }
}

@media (min-width: 600px) and (max-width: 799px) {
  :root {
    font-size: 16px;
  }
}
@media (min-width: 800px) {
  :root {
    font-size: 16px;
  }
}
```

미디어 쿼리를 사용해서 root폰트 크기를 변경한 것이다.
그리고 line-height를 조금 수정해 보도록 하자.

```css
.post h1 {
  font-size: 2rem;
}
.post p {
  font-size: 1rem;
  line-height: 2;
}
```

이러한 작업을 하고 기사를 보면 훨씬 더 나은 모습일 것이다.
![image](https://user-images.githubusercontent.com/48292190/114804176-d876e000-9ddb-11eb-8a71-b5af7fa3cd96.png)

오케이, 이제 제목을 조금 더 꾸며보도록 하자.

```css
.post h1 {
  padding-left: 0.5rem;
  border-left: solid 0.65rem var(--accent-color);
  font-size: 2rem;
}
```

어릴 때, 글만 있는 책을 보면 정말 지루했었는데 그때마다 그림이 정말 고마웠다. 그래서 이번에는 **사진을 넣어보도록 하자.**

![image](https://user-images.githubusercontent.com/48292190/114805053-453eaa00-9ddd-11eb-8158-34b0194057e9.png)

굳! 사진을 넣으니 훨씬 글이 영양가 있어졌다. 이때, 사진의 최대 크기는 콘텐츠의 크기와 동일해야 되는데,

```css
.post img {
  max-width: 100%;
}
```

이렇게만 해주면 알아서 최대크기가 설정된다.

### 빵 부스러기 리스트 출력

이름이..정말 맘에 안들지만 일단 해보도록 하겠다.
![image](https://user-images.githubusercontent.com/48292190/114808956-40c9bf80-9de4-11eb-9b57-43aba142fa3a.png)

```css
.bread ol {
  margin: 0;
  padding: 0;
  list-style: none;
  display: flex;
}
.bread a {
  display: block;
  padding: 5px;
  color: inherit;
  font-size: 0.875px;
  text-decoration: none;
}
.bread a::after {
  margin-left: 10px;
  content: ">";
  font-family: "FontAwesome";
  opacity: 0.3;
}
.bread a:hover {
  background-color: rgba(0, 0, 0, 0.3);
}
```

빵 부스러기 리스트를 다 만들었으니 다음 페이지를 만들어보자.
**(책의 내용상 지금 만드는게 소개 페이지라서 바꿨습니다...)**

### 소개 페이지 만들기

기존에 있던 빵 부스러기 리스트를 지우고 작업을 합니다.

소개 페이지의 테이블은 `반응형`으로 작업했으며 flex레이아웃을 사용했다.

```css
.history {
  background-color: var(--main-color);
  color: var(--text-bright-color);
}

.history .text {
  padding: 20px;
}

.history h2 {
  margin-top: 0;
  margin-bottom: 10px;
  font-size: 1.5rem;
}

.history .photo {
  min-height: 300px;
  background-image: url(img/article_1.jpeg);
  background-position: center;
  background-size: cover;
}

.history table {
  border-collapse: collapse;
  border-top: 1px solid var(--gray-color);
  font-size: 0.875rem;
}
.history th,
.history td {
  padding: 1.8rem 0;
  border-bottom: 1px solid var(--gray-color);
}

.history th {
  padding-right: 1rem;
  text-align: left;
  word-break: keep-all;
}

/* 반응형 */
@media (min-width: 768px) {
  .history .container {
    display: flex;
    max-width: var(--large-width);
    margin-left: auto;
    margin-right: auto;
  }
  .history .photo {
    flex: 3;
  }
  .history .text {
    flex: 2;
    padding: 50px;
  }
}
```

![image](https://user-images.githubusercontent.com/48292190/114839137-640a6400-9e10-11eb-9d47-4c23bd18e4d5.png)

## 문의 페이지 만들기

![image](https://user-images.githubusercontent.com/48292190/114871807-a47bd900-9e34-11eb-8c0a-45fafc6ef82b.png)

### 이제 구글 지도를 추가하는 방법을 보도록 하겠습니다.

![image](https://user-images.githubusercontent.com/48292190/114873868-b52d4e80-9e36-11eb-9d30-6b1f01770dc1.png)

이렇게 구글 지도에 들어가서 공유를 누르고 지도 퍼가기를 클릭한 다음에 HTML복사를 한 다음,
원하는 위치에 복사한 HTML을 붙여넣으면 완성된다.
![image](https://user-images.githubusercontent.com/48292190/114874275-24a33e00-9e37-11eb-8b9d-06ea91216760.png)

이제 지도에 제목을 추가해서 스타일링을 마무리 하도록 하겠다.

## 기사 목록 페이지 만들기

기사 목록 페이지는 기사 개요를 나열하는 페이지다.
최상위 페이지 기반으로 만들 것이며, 3개의 패턴(레이아웃)을 나눠서 개발할것이다.

최상위 페이지인 index.html를 복사한 다음에 list-a.html이라는 파일을 만들어서 히어로 이미지를 제외한 나머지 부분들을
전부 제거하는 작업을 해주면 된다.

```html
<section class="conA compact">
  <div class="container">
    <h1>Hong-JunHyeok</h1>
    <p>개발은 곧 모험이다. 개발자 홍준혁입니다.</p>
  </div>
</section>
```

히어로 이미지 section에 compact라는 클래스 속성을 추가해서 css에 다음과 같은 작업을 해주도록 하자.

```css
.conA.compact {
  height: 450px;
  min-height: 0;
  background-image: linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.1)),
    url(img/article_2.jpg);
  background-position: center;
}
```

이러면 기존에 conA에 있던 css속성에서 덮어쓰기가 되어서 스타일이 적용된다.

이제 페이지의 템플릿을 만들었으니, 기사 개요를 출력하는 방법에 대해서 알아보도록 하자.

### 카드 뷰 만들기

![image](https://user-images.githubusercontent.com/48292190/114979129-4b0fba80-9ec5-11eb-8349-9d01480ecf0b.png)

카드 뷰를 만들때에는 background-image를 조금 다른 방식으로 줄까 한다.

```html
<div
  class="photo"
  style="
                background-image: url(http://flamingotiger.github.io/image/thumb/react-thumb.jpg);
              "
></div>
```

이런식으로 `style`이라는 속성을 사용해서 주소를 대입하는 형식이다.
각 카드뷰마다 이미지가 다를텐데, 그때마다 각 클래스를 파서 css에 `background-image`를 주고... 그런 작업은 효율작인 작업은 아닌것 같다. 그래서 **사용하는 방법이 `background-image`를 style에 박아버리는 방법이다.**

```html
<article>
  <a href="#">
    <div
      class="photo"
      style="
                background-image: url(http://flamingotiger.github.io/image/thumb/react-thumb.jpg);
              "
    ></div>
    <div class="text">
      <h2>React스러운 상태관리 라이브러리 :: Recoil</h2>
      <p>
        비교적 간단한 프로젝트엔 무겁게 느껴질 수 있는 Redux와 MobX, 그리고
        이들은 근본적으로 React를 위해 출시된 것이 아니었습니다...
      </p>
    </div>
  </a>
</article>
```

```css
.listA .photo {
  min-height: 150px;
  background-position: center;
  background-size: cover;
}

.listA h2 {
  font-size: 18px;
}
.listA p {
  font-size: 14px;
  opacity: 0.8;
}
.listA a {
  margin: 10px;
  display: block;
  border: 1px solid var(--gray-color);
  color: inherit;
  text-decoration: none;
}

.listA a:hover {
  opacity: 0.8;
}

.listA .text {
  margin: 10px;
}
```

이런식으로 작성하게 된다면 생각보다 볼만한 카드뷰가 나오게 된다. 마우스를 오버했을때, opacity가 바뀌는 작업까지 해주었다.
추후에 article을 늘리는 작업을 하고 싶다면, 그냥 복붙하고 제목 , 내용 , 이미지를 바꿔주면 된다.

![image](https://user-images.githubusercontent.com/48292190/114980523-8e6b2880-9ec7-11eb-8a4d-243026d9d87e.png)

# 디자인 재구성

- ## 헤더 재구성

  > **색을 재구성한 헤더** > ![image](https://user-images.githubusercontent.com/48292190/114984876-1dc70a80-9ecd-11eb-943d-0c59af17c54f.png)

  > **헤더와 히어로 이미지를 하나로 디자인하기** > ![image](https://user-images.githubusercontent.com/48292190/114985483-d1c89580-9ecd-11eb-8c2f-43f506970028.png) > `background-color : transparent` => 투명한 색

  > **헤더를 화면 위에 고정하기** > `position : fixed`라는 속성을 사용하게 되면, 헤더가 스크롤 되지 않고 그대로 화면에 남아있는다.

  ```css
  .head-fixed,
  .nohero .head-fixed {
    position: fixed;
  }
  .nohero .head-fixed + * {
    margin-top: 70px;
  }
  ```

- ## 기본 색상 재구성

  > **페이지의 기본색 재구성하기**
  > 페이지의 기본색을 바꾸기 위해서는 변수의 값만 바꾸면 된다. 만약, 변수를 안쓰고 일일이 헥스코드를 입력했었으면...엄청 끔찍한 일이 일어났을 것이다.

  ```css
  /* 기본 색상 */
  :root {
    --main-color: #a7304f;
    --accent-color: #b4ac46;
    --dark-main-color: #5a1124;
    --text-bright-color: #fff;
    --icon-color: #fff;
    --icon-bk-color: #ddd;
    --large-width: 1000px;
    --middle-width: 800px;
    --purple-color: #a388f3;
    --gray-color: #ddd;
  }
  ```

  이렇게 색을 바꾸고 바뀐 웹사이트를 한번 보면,
  ![image](https://user-images.githubusercontent.com/48292190/115103681-c8ebc880-9f8e-11eb-9df3-6a358b3340e5.png)

  변수만 바꿔도 **전역적으로 색이 바뀐 모습**을 볼 수 있다.

# HTML CSS 뿌수기

이제 프로젝트를 완료했으니, 우리가 할 작업은 HTML,CSS 그리고 웹 개발에 있어 자잘한 팁까지 정리해보도록 하겠다.

## HTML 레퍼런스

- **기본 문법**

```html
<h1>기사 제목</h1>
```

여기서 `h1`부분이 요소의 이름이다.
그리고 `<h1>`은 시작 태그를 의미하고, `</h1>`는 종료 태그를 의미한다.
`기사 제목` 부분은 콘텐츠 부분이다.

> 1.  태그는 중첩적으로 사용이 가능하다.
> 2.  요소에는 속성이 존재한다. 속성을 추가하면 다양한 정보를 추가할 수 있다.
> 3.  요소의 콘텐츠는 빈 요소로 둘 수 있다.

- **HTML 기본 설정**

  - DOCTYPE 선언 -> 최신 HTML로 이 문서를 작성하겠다는 의미이다.
  - `<head>` -> `<head>`태그 내부에는 메타데이터(페이지와 관련된 정보)등을 입력한다.
  - `<html>` -> 루트 요소를 의미하며, lang속성으로 문서의 언어를 표기하는게 좋다.
  - `<body>` -> `<body>`태그 내부에는 브라우저 화면에 출력할 내용을 작성한다.

  ```html
  <!DOCTYPE html>
  <html lang="ko">
    <head> </head>
    <body></body>
  </html>
  ```

- **메타데이터**

  메타데이터는 페이지와 관련된 다양한 정보 또는 설정을 의미한다. `<head>`태그 안에 작성한다.

  - `<title>`

    **페이지의 타이틀을 의미한다. 필수 사항이며, 생략하면 안된다.**

  - `<style>`

    **웹 페이지 내에서 CSS설정을 작성할 때 사용한다.**

  - `<link>`

    **외부 리소스를 명시할 때 사용한다. 만약 외부 CSS파일을 읽어 들이는 경우**

    ```html
    <link rel="stylesheet" href="~.css" />
    ```

    **위와 같은 방법으로 HTML head에 작성해주면 된다.**

  - `<script>`

    **웹 페이지 내에서 스크립트 설정을 작성할 때 사용한다.**

    ```html
    <script src="~.js"></script>
    ```

  - `<meta>`

    **인코딩 설정, 페이지 정보, 모바일 설정 등과 같은 설정을 하는 태그이다.**

    > **모바일 설정?**
    > 아래의 코드와 같이 모바일 대응이라고 각인시켜주는 설정이다.

        만약 이 설정을 하지 않는다면 **모바일 반응형이 되지 않을것이다.**

        ```html
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        ```

- **섹션**

콘텐츠의 그룹(섹션)을 명시한다.

- `<section>`

  **콘텐츠의 그룹을 명시할 때 사용한다.**

  시각적인 디자인을 목적으로 콘텐츠를 그룹으로 묶을 때에는 div를 사용한다.

- `<nav>`

  **다른 페이지 또는 페이지 내부 요소로의 링크를 모을 때 사용한다.**

  네비게이션 역할을 가진 그룹이라는 것을 명시한다.

- `<aside>`

  **부가/관련 정보라는 것을 명시한다.**

  사이드바의 정보, 광고 등을 명시할 때에도 사용한다.

- `<body>`

  **섹셔닝 루트 라고도 부르는데, 페이지 전체의 콘텐츠라는 것을 명시할 때 사용한다.**

- `<article>`

  **단순히 콘텐츠를 모아놓은 것이 아니라 하나의 완전한 콘텐츠라는 것을 명시한다. 블로그, 뉴스의 기사 등을 명시할 때 사용한다.**

  article로 된 기사는 사파리나 타 웹브라우저에서 리더 기능을 사용할 수 있다.

- **콘텐츠**

  - `<h1>,<h2>,<h3>,<h4>,<h5>,<h6>`

    **제목이라는 것을 명시한다. 제목의 단계에 따라 1~6까지 구분할 수 있다.**

  - `<p>`

    **문장의 단락이라는 것을 명시한다.**

  - `<br>`

    **줄바꿈을 할때 사용하는 빈 요소이다.**

  - `<header>`

    **섹션의 헤더 또는 푸터를 명시할 때 사용한다.**

    > body아래에 바로 넣으면 페이지 전체의 헤더, 푸터라는 것을 명시한다.

  - `<div> , <span>`

    **특별한 의미를 가지지 않는 범용 태그이다. 시멘틱을 명시하고 싶지 않거나 적절한 태그가 없는 경우 사용한다.**

  - `<ol> , <ul> , <li>`

    **리스트 형식의 정보라는 것을 명시할 때 사용한다.**

    ```html
    ul은 순서에 의미가 없는경우
    <ul>
      <li></li>
      <li></li>
      <li></li>
    </ul>
    ```

    ```html
    ol은 순서에 의미가 있는경우
    <ol>
      <li></li>
      <li></li>
      <li></li>
    </ol>
    ```

  - `<a>`

    **링크를 설정한다. URL은 href속성으로 링크 설정이 된다.**

  - `<table> , <tr> , <th> , <td>`

    **표를 구성할 때 사용한다.**

    ```html
    <table>
      <tr>
        <td></td>
        <td></td>
      </tr>
    </table>
    ```

  - `<img>`

    **이미지를 출력하는 태그이다. src속성에 이미지의 URL을 넣어주면 된다.**

  - `<iframe>`

    **인라인 프레임을 사용해서 외부 콘텐츠를 읽어온다. 구글지도나 유튜브 등 퍼가기 코드는 iframe으로 제공된다.**

## CSS 레퍼런스

- **CSS 기본 문법**

```css
h1 {
  font-size: 20px;
}
```

- {} 로 이루어진 블록을 "선언 블록"이라고 한다.
- `h1`이 있는 자리는 "선택자"라고 한다.
- `font-size`가 있는 자리는 "속성"이라고 하고
- `20px`이 있는 자리는 "값"이라고 한다.
- `font-size : 20px;`는 "선언"했다라고 한다.

**CSS 선택자(여러 대상 적용하기)**

```css
h1 {
  font-size: 20px;
}
h2 {
  font-size: 20px;
}
h3 {
  font-size: 20px;
}
```

만약 다음과 같은 상황에서 CSS선택자를 사용하여 더욱 편리하게 바꾸는 방법은

```css
h1,
h2,
h3 {
  font-size: 20px;
}
```

이렇게 사용하면 된다.

## CSS에서 매우 중요한 부분중 하나인 선택자.
- 태그 선택자
  
  **지정한 이름의 요소를 적용 대상으로 한다.**
  ```css
  h1 { ... }
  ```

- 클래스 선택자

  **지정한 클래스 이름을 가진 요소를 적용 대상으로 한다.**
  ```css
  .classA { ... }
  ```

- 전체 선택자

  **모든 요소를 적용 대상으로 지정한다.**
  ```css
  * { ... }
  ```

- 부정 선택자

  **지정한 조건과 일치하지 않는 요소를 적용 대상으로 한다.**
  ```css
  :not( ~ ){ ... }
  ```

- 의사요소 선택자

  **요소 앞뒤에 콘텐츠를 넣기 위한 선택자**
  ```css
  ::before{}
  ::after{}
  ```

- :root 선택자

  **루트 요소인 `<html>`을 적용하기 위한 선택자**
  ```css
  :root{ ... }
  ```

- 반응 선택자

  **커서를 올린 요소를 적용 대상으로 한다.**
  ```css
  :hover{ ... }
  ```

- 후손 선택자

  **A 내부 요소의 B요소를 적용 대상으로 한다.**
  ```css
  A B { ... }
  ```
  ```html
  <A><B></B></A>
  ```

- 인접 선택자

  **A 요소 뒤에있는 B 요소를 적용 대상으로 한다.**
  ```css
  A + B { ... }
  ```
  ```html
  <A></A><B></B>
  ```

- :first-child 유사 선택자

  **같은 단계의 첫 번째 요소를 적용 대상으로 한다.**
  ```css
  :first-child { ... }
  ```

## 미디어 쿼리

@media ( ~ )에서 지정한 조건이 만족할 때만 CSS설정을 적용한다.
```css
@media (<특성 이름> : <속성 값>){
  /* CSS 설정을 작성합니다. */
}
```
만약 넓이로 한다면 width , max-width , min-width 등의 특성 이름을 조건으로 지정한다.

```css
@media (mix-width : 1000px){
  /* 브라우저의 넓이가 1000px이상일때 실행할 CSS코드 */
}
```
## 박스 모델

웹 페이지에서 HTML로 마크업한 콘텐츠마다 박스라는 것이 만들어진다.

박스의 구조는 
![image](http://codingschool.info/content/css/box_model/img/8-1.png)
이렇게 이루어져 있다.

### 박스의 기본 설정 
박스의 기본 설정을 조정할 때 사용하는 속성이다.
- **margin / padding**
> margin은 테두리 외부 , padding은 테두리 안쪽의 여백 크기를 지정한다.
```css
margin : 위 아래 왼쪽 오른쪽
margin : 위 아래 , 왼족 오른쪽 
margin : 위, 왼쪽 오른쪽, 아래
margin : 위, 오른쪽 , 아래, 왼쪽

혹은 

margin-bottom, margin-top과 같은 속성을 사용할 수도 있음
```
- **width / height**
> width와 height로 콘텐츠 박스의 너비와 높이를 지정할 수 있다.
```css
box-sizing: border-box 를 지정하게 되면 테두리 박스의 너비와 높이를 지정할 수 있다.
```
- **border**
> 테두리의 디자인을 지정할 때 사용됩니다.
```css
border : 종류 두께 색; 

위, 아래 , 오른쪽 , 왼쪽 테두리를 개별적으로 지정하고 싶으면
border-bottom , border-left과 같은 속성을 사용할 수도 있음
```

- **background-image**
> background-image는 배경 이미지를 지정한다.
- **background-color**
> 배경 색을 지정한다.
- **background**
> 배경색과 이미지를 한꺼번에 지정할 수 있다.
- **background-size**
> 배경 이미지가 출력되는 크기를 지정한다. 
> cover , contain 등...
- **background-position**
> 이미지를 자르는 위치를 지정한다.
```css
background-position : left top; /*왼쪽 위*/
background-position : center; /*가운데*/
```
- **border-radius**
> 박스의 각 둥글기를 지정한다.
```css
border-radius : <각 둥글기의 반경>;
```
- **box-shadow**
> 박스에 그림자 디자인을 지정한다.
```css
box-shadow : 가로 세로 블러 스프레드 색
```
- **opacity**
> 박스의 투명도를 지정한다.
```css
opacity : <투명도>;
```

## 박스의 종류 
박스의 종류
- 블록 박스
```css
display : block;
```
> 블록박스는 줄바꿈이 들어간다. 
부모 요소의 넓이를 꽉 채워 출력한다.

- 인라인 박스
```css
display : inline;
```
> 인라인 박스는 앞뒤에 줄바꿈이 들어가지 않고, 내용에 맞는 너비를 가지는 것이 특징이다.
> 그리고 width, height,margin 등이 안먹힌다.
- 인라인 블록 박스
```css
display : inline-block;
```
> 인라인 박스와 같지만, width와 height로 너비와 높이를 지정할 수 있으며, margin으로 위아래 마진또한 할 수 있다.
- 박스를 구성하지 않음 
```css
display : none;
```
> none속성은 박스를 구성하지 않는 상태가 된다.

<!-- ## 플렉시블 박스 레이아웃 -->

## 최적화

```

```
