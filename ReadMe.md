# 최신 표준 HTML5+CSS3 디자인

> **왜 배우나요?**
> 최근에 리액트 + Redux로 프로젝트를 진행하면서 느꼈던점이 있다. 
> 너무 js에만 집착하다 보니 웹에 기초가 되는 HTML, 그리고 CSS를 너무 대충하지 않았나...
> 하는 생각을 하게 되었는데 그때에 나를 반성하고자, 그리고 변해보고자 이 [**최신 표준 HTML5+CSS3 디자인**] 를 읽어보면서 기초를 탄탄히 다지는 시간이 되었으면 좋겠다.

## 목차
- [사전 준비](#사전-준비)
- [최상위 페이지 만들기](#최상위-페이지-만들기)
- **콘텐츠 페이지 만들기** (준비중)
- **기사 목록 페이지 만들기** (준비중)
- **디자인 재구성** (준비중)

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
파일을 저장할 Web폴더를 준비하고 HTML파일은 index.html, CSS파일은 style.css라는 이름으로 저장한다.

```html
<!--index.html-->
<!DOCTYPE html>
<html lang="ko">
    <head>
        <meta charset="UTF-8">
        <title>여기에 제목이 들어갑니다.</title>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="style.css">
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
:root{
    --main-color : #123455;
    --accent-color : #123456;
    --dark-color : #000000;
}
```

- `@charset` : CSS파일의 인코딩 종류가 UTF-8이라는 것을 명시.
- `기본색 설정` : :root내부에 작성한 값들은 CSS상에서 사용할 일종의 변수같은 계념이다.
- `주석` : /**/ 의 형태로 작성


## 최상위 페이지 만들기

- ## 히어로 이미지 
페이지에 아주 크게 표시되는 이미지 요소를 의미함. 
![image](https://user-images.githubusercontent.com/48292190/114636634-6b434c00-9d02-11eb-934c-f870397f7e63.png)
(헤더 이미지, 라지 헤더 등으로도 불림)

> **폰트 지정을 하지 않았을 때에 생길수 있는 문제**
환경(윈도우, Mac, Linux등 혹은 검색엔진)에 따라 폰트가 다 달라보일수 있는 문제가 있기때문에 통일감을 주기 위해서 폰트를 지정을 해줘야한다.

> **브라우저 너비에 따라 폰트 크기 변경하기**
vw(화면 너비의 단위)라는 단위를 사용해서 각 장치의 화면 넓이마다 폰트의 크기를 다르게 보이게 할 수 있다.

> **큰 화면에서의 폰트 크기 조정하기**
사이트에서 폰트 크기가 너무 커지면 화면이 주는 압박감이 커지기 때문에 큰 화면에서는 폰트 크기를 고정시키는 작업을 하는 방법이 있다.
이때에는 media쿼리를 사용하면 되는데, 브레이크 포인트를 걸어서 화면의 너비가 몇일때, 스타일링을 다르게 줄 수 있다. 이를 **반응형 웹페이지**라고 한다.

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
:root를 사용하게되면 문서에 루트에 접근한다는 의미이다. 
즉 html{} 과 같은 기능을 하는 것인데, 전역적으로 선언한 선택자라고 보면 될거같다.

### 반투명한 검정색 이미지를 중첩해서 어둡게 만들기
CSS는 포토샵이 아니기때문에 사진을 직접 수정할 순 없다. 그래서 반투명한 검은색 이미지를 겹쳐서 어둡게 만드는 효과는 낼 수 있다.
이때, 반투명한 색을 지정하는 방법은 `rgba()`라는 아이를 사용하면 된다. r은 붉은색 g는 초록색 b는 파란색 그리고 마지막 인자값은 투명도의 값을 조절한다.
> **그레이디언트란 무엇인가요?**
그레이디언트한 서서히 올라오는(내려가는) 느낌을 줄 수 있다.
```css
background-image : linear-gradient(
    rgba(0,0,0,0.1),
    rgba(0,0,0,0.5)),
    url(img/main_3.jpeg);
```
![image](https://user-images.githubusercontent.com/48292190/114655064-67292580-9d26-11eb-9c41-c7b23bd94f58.png)
`linear-gradient`라는 속성을 사용하면 사용 가능하다.

- ## 개요
