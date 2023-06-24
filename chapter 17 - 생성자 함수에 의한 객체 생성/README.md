# Chapter 17 : 생성자 함수에 의한 객체 생성, Summary

<br>

### 처음 알았어요 ❗️
#### 1️⃣ 생성자 함수
- JS의 경우 일반 함수 앞에 new 키워드를 활용하는 경우 해당 일반 함수는 생성자 함수로서 동작한다
- 즉, 일반 함수에서 객체를 반환하는 코드가 없어도 new 키워드와 함께 작성되는 경우 JS 엔진에 의해 생성자로서 동작!

<br>

#### 2️⃣ 생성자 함수에서 인스턴스를 생성하고 반환하는 과정
- 생성자 함수의 스코프로 들어서면 암묵적으로 빈 객체를 생성하고 this와 bind! → 이후 생성자 몸체 코드가 실행
- 몸체에 기술된 내용을 기반으로 this(즉, 비어 있던 객체) 초기화가 진행
- 모든 코드 실행이 완료되면 해당 객체를 반환
    - 단, 명시적으로 return 문이 생성자 함수 내부에 존재하는 경우 반환 타입에 따라 다르게 동작
    - 원시 타입 : 원시 값은 무시되고 this 객체가 반환
    - 객체 타입 : 명시된 객체가 반환 (this 객체는 무시됨)

<br>

#### 3️⃣ 함수 객체의 내부 메소드, [[ Call ]], [[ Construct ]]
- 함수는 일반 객체의 internal slot / method를 모두 가지고 있음 ❗️
- 추가로 함수 호출 및 생성자로서 동작하기 위한 [[ Call ]], [[ Construct ]] 내부 메소드를 가지고 있음
- [[ Call ]] : 이 메소드를 가지는 객체를 callable이라고 부르며 일반 함수와 같이 호출할 수 있다
- [[ Construct ]] : 이 메소드를 가지는 객체를 constructor, 갖지 않는 함수 객체를 non-constructor라고 부름 → 생성자로서 동작할 수 있는 함수의 경우 가지고 있는 내부  메소드!

<br>

#### 4️⃣ constructor / non-constructor 구분
- constructor : 함수 선언문, 함수 표현식, 클래스
- non-constructor : ES6 메소드 축약 표현, 화살표 함수
- 즉, 객체 내부의 축약 표현되어 있는 함수는 생성자로서 동작 불가 ❌
- 단, 객체 내부에서 축약 표현되어 있지 않는 함수는 생성자로서 동작 가능 (ESM 사양에서 메소드로서 인정하지 않기 때문)

#### 5️⃣ ES6 : new.target
- ES6부터 도입된 meta property (IE를 제외한 모던 브라우저에서 지원)
- new 연산자와 생성자 함수로서 호출되었을 경우 : 해당 함수 내부에서 new.target은 함수 자신을 의미
- 그 이외의 경우 : undefined
- <a href="./newTarget.js">new.target 활용 예제 파일</a>
- 참고로, 대부분의 빌트인 생성자 함수 Object, String, Number, Boolean, Function 등은 new 키워드 활용 여부를 점검하고 적절한 값을 반환
- Object, Function의 경우 new 연산자 없이 호출해도 new 연산자가 함께 활용된 것처럼 동작
- Number, String, Boolean 생성자 함수는 new 연산자 활용 여부에 따라 다른 값이 반환됨 → <a href="./builtInConstructor.js">차이를 보여주는 예제 파일</a>