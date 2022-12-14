## 1.  상황에 따라 달라지는 this
- this란 무엇인가요?

    this는 호출한 객체에 대한 정보가 담기며, 기본적으로 실행컨텍스트가 생성될 때, 즉 함수가 호출될 때 결정되는데요.

    함수를 어떤 방식으로 호출하느냐에 따라 값이 달라집니다.

- 전역공간에서의 this는 뭔가요?

    전역컨텍스트를 생성하는 주체가 전역객체이기 때문에 전역공간에서 this는 전역객체를 가리킵니다. 브라우저 환경에서는 전역객체가 window이고, 노드.js에서는 global 입니다.

    - 꼬리질문) 전역변수는 전역객체의 프로퍼티로도 할당이 되는데 그 이유는 무엇인가요?

        전역변수를 선언하면 자바스크립트 엔진은 이를 전역객체의 프로퍼티로 할당하기 때문입니다. 

        자바스크립트에서 모든 변수는 특정 객체의 프로퍼티로서 동작하기 때문입니다. 여기서 특정 객체란 실행 컨텍스트의 렉시컬 인바이어먼트이고, 실행컨텍스트는 변수를 수집해서 렉시컬 인바이어먼트의 프로퍼티로 저장하게 되는데 , 이로써 변수를 호출하면 렉시컬인바이어먼트를 조회를 해서 일치하는 프로퍼티가 있을 경우 그 값을 반환하게 됩니다.

    - 오~ 그럼 전역변수로 선언하면 전역객체의 프로퍼티로 할당된다고 보면 되는건가요?

        네 대부분의 경우는 맞지만, **삭제 명령**의 경우는 다릅니다. 프로퍼티로 할당한 경우에는 삭제가 되지만, 전역변수로 선언한 경우에는 삭제명령이 안되는데요. 사용자가 의도치 않게 삭제하는 것을 방지하기 위해 그렇게 설계되었다고 해석된다고 합니다.

        전역변수를 선언하게 되면, 엔진이 전역객체의 프로퍼티로 할당하면서 추가적으로 컨피규러블 속성을 false로 정의합니다.

- 메서드로 호출할 때 그 메서드 내부에서 this
    - 함수를 실행하는 방법을 말해보세요

        함수를 실행하는 방법에는 크게 **독립성**에 따라 함수로서 호출하는 경우와 메서드로서 호출하는 경우가 있습니다.

        함수는 그 자체로 독립적인 기능을 하는 반면, 메서드는 자신을 호출한 객체에 관한 동작을 수행합니다. → 이게 무슨 뜻일까요?

    - 메서드가 뭔가요?

        메서드는 **객체의 프로퍼티에 할당된 함수**를 말하는데 이 함수가 메서드로 호출이 되었을 때 메서드로 동작합니다. 쉽게는 함수를 호출할 때 앞에 **.을 찍어서 호출했다면 메서드로 호출**한 것이고 점이 없다면 함수로 호출했다고 볼 수 있는데 한마디로 앞에 객체가 명시되어 있다면 메서드로 호출한 것입니다.

    - 메서드에서 this를 호출하면 어떻게 되나요?

        this에는 호출한 주체에 대한 정보가 담기는데 메서드로 호출하는 경우 호출 주체는 **함수명 앞의 객체**입니다.

- 함수로 호출할 때 this
    - 함수 내부에서 this를 호출하면 this에 어떤 값이 담기나요

        함수로서 호출하는 것은 개발자가 직접 코드에 관여해서 실행한 것이고 호출 주체를 명시하지 않았기 때문에 호출주체의 정보를 알 수 없습니다. this가 지정되지 않은 경우에는 **전역객체**를 가리키기 때문에 함수에서의 this는 **전역객체**를 가리키게 됩니다.

## 2. 명시적으로 this를 바인딩하는 방법
- call 메서드
    
    call은 메서드의 호출 주체인 함수를 즉시 실행하도록 하는 명령인데, 콜 메서드의 첫번 째 인자를 디스로 바인딩해줍니다. 이렇게 명시적으로 임이의 객체를 this로 지정할 수 있습니다.
    
- apply 메서드
    
    apply는 call과 기능적으로 완전히 동일한데 첫번째 인자를 제외한 나머지 모든 요소를 매개변수로 받는 콜과는 달리 두번째 인자를 배열로 받아서 매개변수로 지정한다는 점에서 차이가 있습니다.
    
- 생성자 내부에서 call이나 apply를 쓰는 경우가 무엇이 있나요
    
    생성자 내부에 다른 생성자와 공통된 내용이 있을 경우, call이나 apply를 통해 반복을 막아줄 수 있습니다. 첫번 째 인자에 this를 넣고, 나머지는 각자 맞는 형식으로 인자로 넣어주면 생성자 함수 내부에서 다른 생성자 함수를 호출해 인스턴스의 속성을 정의하도록 구현할 수 있습니다.

## 스터디에서 나온 질문
1. 화살표함수에서 this는 어떻게 작동할까요.
2. 명시적이로 this를 바인딩하는 방법은 어떤게?
3. 클로저로 this를 어떻게 명시적으로 바인딩하나요?
4. 클로저는 뭘까요
5. 클로저는 어떤 경우에 사용하나요(변수 은닉 외에 다른 사용경우도 알아보시면 좋을 것 같네용)
6. 1급객체는 뭔가요?