# 실행컨텍스트

- 활성화 된 실행컨텍스트에는 뭐가 담기나요?
    - Variable Environment, LexicalEnvironment, ThisBinding
    - Variable: 식별자, 외부환경, 스냅샷
    - Lexical : 실시간
    - This : this, 객체
    - V와 L의 내부에는 environmentRecord, outerEnvironmentReference로 구성.
- LexicalEnvironment의 environmentRecord에는 무엇이 담기나요?
    - 현재 컨텍스트와 관련된 코드의 식별자 정보들이 저장되는데, 매개변수의 이름, 함수선언, 변수명 등을 컨텍스트 내부 전체를 쭉 훑어나가면서 순서대로 수집.
- outerEnvironmentReference에는 무엇이 담기나요
    - 바로 직전 컨텍스트(= 해당 함수가 선언된 위치)의 LexicalEnvironment의 정보를 참조
# 10.02

### 실행컨텍스트

1. Lexical Environment랑 Variable Envi 가 있는데 Variable Envrionment의 역할
2. 스코프의 개념
3. 스코프 체인을 Rexical Environment와 엮어서 설명
(스코프체인을 outer environment라는 키워드를 섞어서 설명)
4. Lexical Environment에서 어떤 정보를 가지고 실행컨텍스트의 스코프를 참조하나요
5. outer environment에 대해 알고 계신가요
6. 호이스팅이란?
    - 코드진행수월, environmentRecord의 수집과정, 실행컨텍스트, 최상단, 해석, 선언부
7. var와 let,  const가 다르게 작동하는데 어떻게 작동하나요
8. var의 스코프는 블록레벨 스코프가 아닙니다. 이걸 es6이전 문법에서 블록레벨 스코프를 가지게 할 수 있는 방법을 낸 게 있다. 무엇인지 아시나요?(즉시실행 함수)
9. 실행컨텍스트 하면 이벤트 루프가 항상 나오는데 이벤트 루프에 대해 콜스택이라는 키워드를 엮어 설명해주세요
10. 마이크로 태스크와 매크로 태스크를 프로미스 등 엮어서 설명
11. 실행컨텍스트에 들어있는 variable environment에 대해 설명해주세요
12. 실행컨텍스트에서 콜스택이라는 개념이 나옵니다. 콜스택이 뭐고 어떤 역할을 하는지요?
13. 콜스택과 힙 간의 관계
14. 비동기함수를 처리하는 순서가 마이크로 태스크랑 매크로태스크가 다른데 키워드를 말씀해주시면서 설명
15. 함수 선언문과 표현식은 어떻게 다를까요
16. 이벤트 루프의 개념
17. 자바스크립트의 map이 어떻게 구현되어 있나요

