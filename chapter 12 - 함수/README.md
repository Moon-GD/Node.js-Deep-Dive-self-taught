# Chapter 12 : 함수, Summary

<br>

### 처음 알았어요 ❗️
#### 1️⃣ arguments 객체
- 함수가 호출될 때마다 함수 인자의 정보를 저장한 상태로 생성되는 객체
- 다만, 함수의 가독성 및 협업을 위해 spread 연산자를 활용하여 인자 정보를 활용하는 것이 권장됨
- 개념적으로만 숙지하고 있자!

<br>

#### 2️⃣ 매개변수 기본 값 설정
- ES6(2015)에 도입된 개념으로 매개 변수의 기본 값 설정이 가능
- 값이 전달되지 않았거나, undefined가 전달된 경우에 기본 값이 매개 인자로 전달된다.

<br>

#### 3️⃣ 즉시 실행 함수의 원리
- 함수 표현식은 JS 엔진에 의해 값으로 인식되면 함수 객체를 생성함!
- 이렇게 생성된 객체를 활용한 것이 즉시 실행 함수의 원리
- 그렇다면 값으로 인식시키는 방법은? : 연산자를 활용하여 값으로 인식되는 함수임을 알려주는 것
- <a href="./IIFE.js">예제</a>

<br>