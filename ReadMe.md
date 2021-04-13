# 최신 표준 HTML5+CSS3 디자인

> **왜 배우나요?**
> 최근에 리액트 + Redux로 프로젝트를 진행하면서 느꼈던점이 있다. 
> 너무 js에만 집착하다 보니 웹에 기초가 되는 HTML, 그리고 CSS를 너무 대충하지 않았나...
> 하는 생각을 하게 되었는데 그때에 나를 반성하고자, 그리고 변해보고자 이 [**최신 표준 HTML5+CSS3 디자인**] 를 읽어보면서 기초를 탄탄히 다지는 시간이 되었으면 좋겠다.

## 목차
- **사전 준비**
- **최상위 페이지 만들기(콘텐츠)**
- **최상위 페이지 만들기(네비게이션)**
- **콘텐츠 페이지 만들기**
- **기사 목록 페이지 만들기**
- **디자인 재구성**

1. ## 사전 준비 

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



