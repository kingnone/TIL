# Flexible box for CSS layout

## CSS Flexbox
* 요소를 행과 열 형태로 배치하는 1차원 레이아웃 방식
  * 요소 간 '공간 배열'과 '정렬'

<br/>

## Flexbox 기본 사항
- main axis (주 축)
  - flex item들이 배치되는 기본 축
  - main start에서 시작하여 main end 방향으로 배치
- cross axis (교차 축)
  - main axis에 수직인 축
  - cross start에서 시작하여 cross end 방향으로 배치
- flex container
  - display : flex; 혹은 display: inline-flex; 가 설정된 부모요소
  - 이 컨테이너의 1차 자식 요소들이 flex item이 됨
  - flexbox 속성 값들을 사용하여 자식 요소 flex item들을 배치
- flex item
  - flex container 내부에 레이아웃 되는 항목

<br/>

## Flexbox 속성
- Flex container 관련 속성
  - display, flex-direction, flex-wrap, justify-content, align-items, align-content
- Flex item 관련 속성
  - oalign-self, flex-grow, flex-shrink, flex-basis, order

<br/>

##  1.Flex Container 지정
- flex item은 행으로 나열
- flex item은 주축의 시작 선에서 시작
- flex item은 교차축의 크기를 채우기 위해 늘어남

<br/>

## 2.Flex-direction 지정
- flex item이 나열되는 방향을 지정
- column으로 지정할 경우 주 축이 변경됨
- \-reverse로 지정하면 시작 선과 끝 선이 서로 바뀜

<br/>

## 3.Flex-wrap
- flex item 목록이 flex container의 하나의 행에 들어가지 않을 경우 다른 행에 배치할지 여부 설정

<br/>

## 4.Justify-content
- 주 축을 따라 flex item과 주위에 공간을 분배

<br/>

## 5.Align-content
- 교차 축을 따라 flex item과 주위에 공간을 분배
- flex-wrap이 wrap 또는 wrap-reverse로 설정된 여러 행에만 적용됨
- 한 줄 짜리 행에는 (flex-wrap이 nowrap으로 설정된 경우) 효과 없음

<br/>

## 6.Align-items
- 교차 축을 따라 flex item 행을 정렬

<br/>

## 7.Align-self
- 교차 축을 따라 개별 flex item을 정렬

<br/>

## 목적에 따른 분류
- 배치 설정
  - flex-direction
  - flex-wrap
- 공간 분배
  - justify-content
  - align-content
- 정렬
  - align-items
  - align-self

<br/>

### 속성별 정리
- justify : 주축
- align ; 교차 축
- content : 여러 행
- items : 행 하나
- self : 요소 하나

<br/>

## 8.Flex-grow
- 여백을 비율에 따라 분배하는 기능

<br/>

## 9.Flex-basis
- flex item의 초기 크기 값을 지정
- flex-basis와 width 값을 동시에 적용한 경우 flex-basis가 우선

2023.02.28