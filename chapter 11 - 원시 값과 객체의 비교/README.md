# Chapter 11 : 원시 값과 객체의 비교, Summary

<br>

### 처음 알았어요 ❗️
#### 1️⃣ 변수명을 활용한 복사에서..
- 원시 값을 변수에 할당 후 다른 변수로 복사하면 값에 의한 복사가 발생 (깊은 복사라는거지!)
    - 과정 : 참조가 되는 변수의 메모리 주소 전달 → 새로운 변수는 메모리 주소를 토대로 값 참조 → 새로운 메모리 위치에 값을 저장하고 해당 위치를 가리키게 된다.
    - 이 때 각자의 값은 서로 다른 메모리 위치를 차지하고 있다는 점이 정말 중요 ⭐️
- 객체를 변수에 할당 후 다른 변수로 복사하면 참조 값에 의한 복사가 발생 (얕은 복사라는 의미!)

<br>

#### 2️⃣ 원시 값을 담고 있는 변수 재 할당 과정
- 새로운 값을 저장할 메모리 확보
- 메모리 확보 이후 값을 저장하고, 이전의 변수는 새로운 주소 값을 가리키게 됨.
- 즉, 이전의 메모리 주소의 값을 치환하는 것이 아니라 새로운 주소를 가리키게 된다
- 이러한 과정을 거치는 이유는? 원시 값 자체가 immutable 한 특성을 가지기 때문!

<br>

#### 3️⃣ V8 Engine의 Hidden Class!
- 자바스크립트의 객체 생성 및 동적인 변화를 줄 수 있는 것은 정말 큰 유연함을 제공! 다만, 이론적으로 성능의 저하를 가져올 수도 있다
- 예를 들어 동적으로 무언가가 생성될 때마다 적당한 크기의 메모리를 할당하고 값을 저장하게 된다. 이 때 메모리 할당을 위한 오버헤드가 발생하는 거임!
- 다만, V8 엔진은 객체가 생성될 때마다 객체의 구조 정보를 분석 및 파악하여 정보를 내부적으로 저장하고 있음
    - 이후, 같은 구조의 객체가 활용될 때 내부 정보를 활용하여 조금 더 용이하게 코드 실행을 이어나갈 수 있음