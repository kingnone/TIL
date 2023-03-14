# JavaScript and Dom

## DOM
* 웹 페이지(Document)를 구조화 된 객체로 제공하며 프로그래밍 언어가 웹 페이지를 사용할 수 있게 연결시킴

<br/>

## 브라우저가 웹 페이지를 불러오는 과정
* 문서(Document)는 웹 브라우저를 통해 해석되어 화면에 나타남 Dom은 이러한 문서를 조작하는 방법을 제공하는 API

<br/>

## 브라우저는 HTML 문서를 해석하여 DOM tree라는 객체의 트리로 구조화 함

<br/>

## DOM에서 모든 요소, 속성, 텍스트는 하나의 객체이며 모두 document 객체의 자식

<br/>

## 웹 페이지를 동적으로 만드는 것 = 웹 페이지를 조작한느 것
* 조작하기 위한 순서
1. 조작 하고자 하는 요소를 선택 또는 탐색
2. 선택된 요소의 콘텐츠 또는 속성을 조작 

<br/>

## 'document' object
* 웹 페이지 객체
* DOM tree의 진입점
* 페이지를 구성하는 모든 객체 요소를 포함

<br/>

## 요소 하나 선택
* document.querySelector()

### document.querySelector(selector)
* 제공한 선택자와 일치하는 element 한 개 선택
* 제공한 CSS selector를 만족하는 첫 번째 element 객체를 반환 (없다면 null 반환)

<br/>

## 요소 여러 개 선택
* document.querySelectorAll()

### document.querySelectorAll(selector)
* 제공한 선택자와 일치하는 여러 element를 선택
* 매칭 할 하나 이상의 셀렉터를 포함하는 유효한 CSS selector를 인자(문자열)로 받음
* 제공한 CSS selctor를 만족하는 NodeList를 반환

<br/>

## 'classList' property
* 요소의 클래스 목록을 DOMTokenList(유사 배열) 형태로 반환
* add()와 remove() 메서드를 사용해 지정한 클래스 값을 추가 혹은 제거

<br/>

## ClassList 메서드 정리
* element.classList.add()
  * 지정한 클래스 값을 추가
* element.classLsit.remove()
  * 지정한 클래스 값을 제거

<br/>

## 일반 속성 조회
* .getAttribute()

## 일반 속성 설정(수정)
* .setAttribute()

## 일반 속성 삭제
* removeAttribute()

<br/>

## 속성 조작 메서드 정리
* Element.getAttribute()
  * 해당 요소에 지정된 값을 반환
* Element.setAttribute()
  * 지정된 요소의 속성 값을 설정
  * 속성이 이미 있으면 값이 업데이트 / 그렇지 않으면 지정된 이름과 값으로 새 속성이 추가
* Element.removeAttribute()
  * 요소에 지정된 이름을 가진 속성 제거

<br/>

## 'textContent' property
* 요소의 텍스트 콘텐츠를 표현

<br/>

## DOM 요소 조작 생성 
* .createElement()

## DOM 요소 조작 추가
* .appendChild()

## DOM 요소 조작 생성 
* .removeChild()

<br/>

## 'style' property
* 해당 요소의 모든 스타일 속성 목록을 포함하는 속성

<br/>

## 정리 
1. 속성(attribute) 조작
  * 클래스 속성 조작 : classList & add() & remove()
  * 일반 속성 조작 : getAttribute() & setAttribute() & removeAttribute()
2. HTML 콘텐츠 조작
  * textContent
3. DOM 조작
  * createElement() & appendChild() & removeChild()
4. style 조작

2023.03.13