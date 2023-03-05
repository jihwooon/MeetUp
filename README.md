# MeetUp

## 1. TDD(TestDriven-Development)란?

---

### [ TDD를 해야하는 이유 ]

TDD(`Test Driven Development`)는 소프트웨어 개발 방법론 중 하나로, 소프트웨어 개발 과정에서 테스트를 먼저 작성하고 이를 통과하는 코드를 작성하는 방법입니다. TDD는 개발자가 더욱 견고하고 유연한 코드를 작성할 수 있도록 도와줍니다.

- TFD(`Test First Development`) + 리팩토링
- TDD는 디버깅 시간을 단축시켜줍니다.
- 테스트코드가 문서화 기능도 같이 합니다.
- 기능 변화에 두려움을 없애줍니다.

### [ **TDD 원칙 ]**

- 원칙 1 - 실패하는 단위 테스트를 작성할 때까지 **프로덕션 코드**(`production code`)를 작성하지 않는다.
- 원칙 2 - 컴파일은 실패하지 않으면서 실행이 실패하는 정도로만 단위 테스트를 작성한다.
- 원칙 3 - 현재 실패하는 테스트를 통과할 정도로만 실제 코드를 작성한다.

### [ ****TDD 사이클**** ]

### **Red → Green → Refactoring**

****TDD 사이클 구현 순서****

- 실패하는 테스트를 구현한다. (`Red`)
    
    ```tsx
    assertEquals(3, add(1,2));
    ```
    
    작성한 테스트를 실행합니다. 이때 테스트는 실패할 것입니다. 이 실패는 아직 구현되지 않은 기능이기 때문입니다.
    
    - 컴파일부터 안 된다.
    - add의 껍데기만 만들면 기능이 없어서 안 된다.
    - **“어떻게 해야 빨리 Green으로 갈 수 있을까?”** 를 고민 합니다.
- 테스트가 성공하도록 프로덕션 코드를 구현한다.(`Green`)
    
    ```tsx
    function add(x, y) {
      return 3;
    }
    ```
    
    실패한 테스트를 통과할 수 있는 코드를 작성합니다. 이때 코드는 기능을 구현하는 것입니다.
    
- **프로덕션 코드**와 **테스트 코드**를 리팩토링한다. (`Refactoring`)
    
    ```tsx
    function add(x, y) {
      return x + y; // 1 + 2
    }
    ```
    
    작성한 코드를 리팩토링합니다. 이때 리팩토링은 코드의 가독성, 유지보수성, 확장성을 향상시키는 과정입니다.
    
    - 중복을 제거를 합니다.
    - 중복을 드러내야 합니다.
    - **의도**를 드러내면 중복이 드러납니다.