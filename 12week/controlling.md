# Controlling event

<br/>

## 일상속의 이벤트
* 버튼을 눌러서 도어락을 열거나, 전화기의 버튼을 눌러서 통화를 시작하는 것
* 키보드를 사용하여 글을 쓰거나, 리모컨을 사용하여 채널을 변경하는 것
* 알람 시계를 설정하여 특정 시간에 알람을 받는 것

<br/>

## 웹에서의 이벤트
- 버튼을 클릭했을 때 모달이 출력되는 것
- 마우스 커서의 위치에 따라 드래그 앤 드롭하는 것
- 사용자가 입력한 값에 따라 새로운 요소를 생성하는 것

<br/>

## event
- 무언가 일어났다는 신호, 사건 (모든 DOM 요소는 이러한 신호를 만들어 냄)

<br/>

## event 종류
- 마우스, 인풋, 키보드, 터치 등

<br/>

## event handler
- 이벤트가 발생했을 때 실행되는 함수 (사용자의 행동에 어떻게 반응할지를 JS 코드로 표현한 것)

<br/>

## .addEventListener()
- 대표적인 이벤트 핸들러 중 하나 (특정 이벤트를 DOM 요소가 수신할 때마다 콜백 함수를 호출)

<br/>

## EventTarget.addEventListener(type, handler)
- 대상에 특정 이벤트가 발생하면, 할 일을 등록한다

<br/>

## .preventDefault()
* 현재 Event의 기본 동작을 중단

2023.03.16