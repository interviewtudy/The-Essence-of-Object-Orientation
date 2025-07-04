# 역할, 책임, 협력

- 객체지향 설계의 전체적인 품질을 결정하는 것은 개별 객체의 품질이 아니라 여러 객체들이 모여 이뤄내는 협력의 품질임

## 협력

### 요청하고 응답하며 협력하는 사람들

- 협력은 한 사람이 다른 사람에게 도움을 요청할 때 시작됨
- 요청을 받은 사람은 일을 처리한 후 요청한 사람에게 필요한 지식/서비스를 제공하는 것으로 요청에 응답함
- 요청을 받은 사람 역시 다른 사람의 도움이 필요한 경우가 생기면 요청을 보내므로, 협력은 다수의 요청과 응답의 흐름으로 구성

## 책임

### 책임의 분류

- 책임: 객체에 의해 정의되는 응집도 있는 행위의 집합
- 객체의 책임은 객체가 무엇을 알고 있는가(knowing)와 무엇을 할 수 있는가(doing)로 구성됨
  - 하는 것(doing)
    - 객체를 생성하거나 계산을 하는 등의 스스로 하는 것
    - 다른 객체의 행동을 시작시키는 것
    - 다른 객체의 활동을 제어하고 조절하는 것
  - 아는 것(knowing)
    - 개인적인 정보에 관해 아는 것
    - 관련된 객체에 관해 아는 것
    - 자신이 유도하거나 계산할 수 있는 것에 관해 아는 것
- 책임은 일반적으로 외부에서 접근 가능한 공용 서비스의 관점에서 이야기 함
- 책임은 객체의 공용 인터페이스를 구성

### 책임과 메시지

- 메시지 전송: 객체가 다른 객체에게 주어진 책임을 수행하도록 요청을 보내는 것
- 메시지는 협력을 위해 한 객체가 다른 객체로 접근할 수 있는 유일한 방법
- 하나의 책임이 여러 메시지로 분할되는 것이 일반적

## 역할

### 역할이 답이다

- 역할은 협력 내에서 다른 객체로 대체할 수 있음을 나타내는 일종의 표식
- 역할을 개념을 통해 협력을 추상화함으로써 단순성, 유연성, 재사용성을 높임

### 대체 가능성

- 역할은 본질적으로 다른 객체에 의해 대체 가능함을 의미
- 객체가 역할을 대체하기 위해서는 행동이 호환되어야 함
- 객체는 역할이 암시하는 책임보다 더 많은 책임을 가질 수 있음
- 역할의 대체 가능성은 행위 호환성을 의미하고, 행위 호환성은 동일한 책임의 수행을 의미

## 객체의 모양을 결정하는 협력

### 협력을 따라 흐르는 객체의 책임

- 객체 설계 순서: 협력 설계(객체들이 주고받을 요청과 응답의 흐름 결정) -> 행동 결정 -> 행동을 수행하는 데 필요한 데이터 결정 -> 클래스의 구현 방법 결정
- 객체의 행위에 초점을 맞추기 위해서는 협력이라는 실행 문맥 안에서 책임을 분배해야 함
- 객체를 충분히 협력적으로 만든 후에 협력이라는 문맥 안에서 객체를 충분히 자율적으로 만들어, 충분히 자율적인 동시에 충분히 협력적인 객체를 창조

## 객체지향 설계 기법

- 책임-주도 설계(Responsibility-Driven Design): 협력에 필요한 책임들을 식별하고 적합한 객체에게 책임을 할당하는 방식
- 디자인 패턴(Design Pattern): 반복적으로 사용하는 해결 방법을 정의해 놓은 설계 템플릿 모음
- 테스트-주도 개발(Test-Driven Development): 테스트를 먼저 작성하고 테스트를 통과하는 구체적인 코드를 추가하면서 애플리케이션을 완성해가는 방식

### 책임-주도 설계

- 기능을 책임으로 분할하고, 분할된 책임을 적절한 객체에게 할당
- 객체가 책임을 수행하는 도중에 스스로 처리할 수 없는 정보나 기능이 필요한 경우 적절한 객체를 찾아 필요한 작업을 요청

### 디자인 패턴

- 반복적으로 발생하는 문제와 그 문제에 대한 해법의 싸응로 정의
- 해결하고자 하는 문제를 명확하게 서술하고, 패턴을 적용가능한 상황과 적용 불가능한 상황을 함께 설명
- 반복해서 일어나는 특정한 상황에서 어떤 설계가 왜 더 효과적인지 이유를 설명

### 테스트-주도 개발

- 실패하는 테스트를 작성하고, 테스트를 통과하는 가장 간단한 코드를 작성한 후, 리팩터링을 통해 중복을 제거하는 것
- 테스트를 작성하는 것에 초점을 맞추는 것이 아니라 책임을 수행할 객체 또는 클라이언트가 기대하는 객체의 역할이 메시지를 수신할 때 어떤 결과를 반환하고 그 과정에서 어떤 객체와 협력할 것인지에 대한 기대를 코드의 형태로 작성하는 것
- 책임-주도 설계의 기본 개념을 따름
