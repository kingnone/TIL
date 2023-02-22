# World Wide Web
* 인터넷으로 연결된 컴퓨터들이 정보를 공유하는 거대한 정보 공간

<br/>

# Web site
* 인터넷에서 여러 개의 Web page가 모인 것으로, 사용자들에게 정보나 서비스를 제공하는 공간

<br/>

# Web page
* HTML, CSS, JavaScript 등의 웹 기술을 이용하여 만들어진, 하나의 인터넷 문서

## 
* Web site
  * 여러 개의 "Web page"가 모여서 구성
* Web page
  * "Web site"를 구성하는 하나의 요소
* Web
  * "Web site"와 "Web page"를 포함하는 상위 개념

<br/>

# HTML
* Hyper Text Markup Language 웹 페이지의 의미와 구조를 정의하는 언어

<br/>

# Hypertext
* 웹 페이지를 다른 페이지로 연결하는 링크
* 참조를 통해 사용자가 한 문서에서 다른 문서로 즉시 접근할 수 있는 텍스트

<br/>

# Markup Language
* 태그 등을 이용하여 문서나 데이터의 구조를 명시하는 언어

<br/>

# HTML Element
* 하나의 요소는 여는 태그와 닫는 태그 그리고 그 안의 내용으로 구성됨
* 닫는 태그는 태그 이름 앞에 슬래시가 포함되며 닫는 태그가 없는 태그도 존재

<br/>

# HTMNL Attribute
* 규칙
  * 요소 이름 다음에 바로 오는 속성은 요소 이름과 속성 사이에 공백이 있어야 함
  * 하나 이상의 속성들이 있는 경우엔 속성 사이에 공백으로 구분함
  * 속성 값은 열고 닫는 따옴표로 감싸야 함
* 목적
  * 나타내고 싶지 않지만 추가적인 기능, 내용을 담고 싶을 때 사용
  * CSS가 해당 요소를 선택하기 위한 값으로 활용

<br/>

# HTML 문서의 구조
* <!DOCTYPE html>
  * 해당 문서가 html로 문서라는 것을 나타냄
* <html></html>
  * 전체 페이지의 콘텐츠를 포함
* <title></title>
  * 브라우저 탭 및 즐겨찾기 시 표시되는 제목으로 사용
* <head></head>
  * HTML 문서에 관련된 설명, 설정 등
  * 사용자에게 보이지 않음
* <body></body>
  * 페이지에 표시되는 모든 콘텐츠

<br/>

# HTML Text structure
* HTML의 주요 목적 중 하나는 텍스트 구조와 의미르 제공하는 것
* 예를 들어 \<h1> 은 단순히 텍스트를 크게 만드는 것이 아닌 해당 문서의 최상위 제목이라는 의미를 부여하는 것

# 대표적인 HTML Text structure
* Heading & Paragraphs : h1~6, p
* List : ol, ul, li
  * Unordered
  *ordered
* Emphasis & Importance : em, strong

<br/>

# CSS
* Cascading Style Sheet 웹 페이지의 디자인과 레이아웃을 구성하는 언어

## CSS 구문
```
h1 {
  color: blue;
  font-sizq: 15px;
}
```

<br/>

## CSS 적용 방법
1. 인라인(Inline) 스타일
2. 내부(Internal) 스타일 시트
3. 외부(Extenal) 스타일 시트

<br/>

## CSS Selectors
* HTML 요소를 선택하여 스타일을 적용할 수 있도록 함

<br/>

## CSS Selectors 종류
* 기본 선택자
  * 전체(*)선택자
  * 요소(tag)선택자
  * 클래스(class)선택자
  * 아이디(id)선택자
  * 속성(attr)선택자
* 결합자 (Combinators)
  * 자손 결합자 (" "(space))
  * 자식 결합자 (>)

<br/>

## CSS Selectors 특징
* 요소 선택자
  * 지정한 모든 태그를 선택
* 클래스 선택자
  * 주어진 클래스 속성을 가진 모든 요소를 선택
  * 예).index는 class="index"를 가진 모든 요소를 선택
* 아이디 선택자
  * 주어진 아이디 속성을 가진 요소 선택
  * 문서에는 주어진 아이디를 가진 요소가 하나만 있어야 함
  * 예)#index는 id="index"를 가진 요소를 선택
* 자손 선택자 (The " "(space) combinator)
  * 첫 번째 요소의 자손 요소들 선택
  * 예)p span은 <p> 안에 있는 모든 <span>를 선택 (하위 레벨 상관 없이)
* 자식 선택자 (The ">" combinator)
  * 첫 번째 요소의 직계 자식만 선택
  * 예)ul > li 은 <ul>안에 있는 모든 <li>를 선택 (한단계 아래 자식들만)

<br/>

# Cascade(게단식) & Specificity(우선순위)
* 동일한 요소에 적용 가능한 같은 스타일을 두 가지 이상 작성 했을 때 어떤 규칙이 이기는지 결정하는 것

## Cascade(게단식)
* 동일한 우선 순위를 같는 규칙이 적용될 때 CSS에서 마지막에 나오는 규칙이 사용
* 아래 예시에서 h1태그 내용의 색은 blue가 적용됨
```
h1 {
  color: red;
}
h1 {
  color: blue;
}
```

## Specificity(우선순위)
* 선택자 별로 정해진 우선순위 점수에 따라 점수가 높은 규칙이 사용
* 아래 예시에서 h1 태그 내용의 색은 red가 적용됨
```
.make-red {
  color: red;
}
h1 {
  color: blue;
}
```

<br/>

# 우선순위가 높은 순
1. Importance (cascade의 구조를 무시하고 모든 우선순위 점수 계산을 무효화하는 가장 높은 우선순위 반드시 필요한 경우가 아니면 절대 사용하지 않는 것 을 권장)
  * !important
2. 우선 순위
  * 인라인 스타일 > id 선택자 > class 선택자 > 요소 선택자
3. 소스 코드 순서

<br/>

# 상속
* 기본적으로 CSS는 상속을 통해 부모 요소의 속성을 자식에게 상속함
* 이를 이용해 코드의 재사용성을 높임
* 상속 되는 속성
  * Text 관련 요소 (font, color, text-align, opacity, visibility) 등
* 상속 되지 않은 속성
  * Box model 관련 요소 (width, height, margin, padding, border, box-sizing, display), position 관련 요소 (position, top/right/bottom/left z-index) 등

<br/>

# HTML 관련 사항
* HTML 요소 이름은 대소문자를 구분하지 않지만 대문자 사용을 권장
* HTML 속성의 따옴표는 작은 따옴표와 큰 따옴표를 구분하지 않지만 큰 따옴표 권장
* HTML은 프로그래밍 언어와 달리 에러를 반환하지 않기 때문에 작성에 주의

<br/>

# CSS 인라인 스타일은 사용하지 말 것
* 문서 유지보수가 힘들어짐
* CSS와 HTML 구조 정보가 혼합되어 작성되기 때문에 코드를 이해하기 어렵게 만듦

<br/>

# 속성은 되도록 Class만 사용하도록 함
* 개발 시 id, 요소 선택자 등 여러 선택자들과 함께 사용할 경우 우선순위 규칙에 따라 예기치 못한 스타일 규칙이 적용되어 전반적인 유지보수가 어려워 질 수 있기 때문
* 문서에서 단 한번 유일하게 적용될 스타일에 경우에만 id 선택자 사용을 고려

<br/>

# CSS 상속 여부는 MDN 문서에서 확인
* MDN 각 문서 하단에 속성별로 상속 여부를 확인할 수 있음

<br/>

2023.02.22