# 2부 벽돌부터 시작하기: 프로그래밍 
- 패러다임이란 프로그래밍을 하는 방법으로, 대체로 언어에는 독립적이다.
- 패러다임은 어떤 프로그래밍 구조를 사용할지, 그리고 언제 이 구조를사용해야 하는지를 결정한다.

# 3장) 패러다임 개요
- 이 장에서는 세 가지 패러다임인 구조적 프로그래밍, 객체지향 프로그래밍, 함수형 프로그래밍에 대해 설명한다.

- 구조적 프로그래밍
  - 구조적 프로그래밍은 제어흐름의 직접적인 전환에 대해 규칙을 부과한다.

- 객체 지향 프로그래밍
  - 객체 지향 프로그래밍은 제어흐름의 간접적인 전환에 대해 규칙을 부과한다.


- 함수형 프로그래밍
  - 세 패러다임 중 가장 먼저 만들어졌다.
  - 함수형 프로그래밍은 할당문에 대해 규칙을 부과한다.

- 생각할 거리
  - 각 패러다임은 프로그래머에게 권한을 박탈할 뿐, 어느 패러다임도 새로운 권한을 부여하지 않는다.
  - 각 패러다임은 부정적인 의도를 가지는 일종의 추가적인 규칙을 부과한다. (무엇을 해서는 안되는지...)
  
- 결론
  - 세 가지 패러다임과 아키텍처의 세 가지 큰 관심사가(함수, 컴퓨넌트 분리, 데이터 관리)가 어떻게 서로 연관되는지에 주목하자.


# 4장) 구조적 프로그래밍
- 서론
  - 구조적 프로그래밍을 발견 한, 데이크스트라에 대한 설명 (원시적인 환경에서도 위대한 발견을 해냈다.)
  
- 증명
  - 프로그램들의 어려운 조건들을 데이크스트라는 증명(proof)이라는 수학적인 언리를 적용하여 이 문제를 해결하고자 했다.
  - goto 문장이 모듈을 더 작은 단위로 재귀적으로 분해하는 과정에 방해가 되는 경우가 있다는 사실을 발견 (증명 기법인 분할 정복 접근법 사용 못함)
    - if/then/else와 do/while 같은 분기와 반복이라는 단순한 제어 구조를 사용하면 문제가 되지 않는다는 것을 발견
      - 이러한 구조는 순차 실행과 결합했을 때 특별하다는 사실을 깨달았다. (데이스트라)
  - 모든 프로그래미을 순차, 분기, 반복 이라는 세 가지 구조만으로 표현할 수 있다. (뵘과 야코피니)
    - 구조적 프로그래밍의 탄생
  - 순차 구문
    - 단순한 열거법을 이용
    - 각 순차 구문의 입력을 순차 구문의 출력까지 수학적으로 추적한다. (일반적 수학적 증명 방식과 같다.)
  - 분기
    - 열거법을 재적용
    - 분기를 통한 각 경로를 열거
  - 반복
    - 귀납법을 사용 (관찰과 경험을 통해 자료를 수집하고, 수집한 자료에서 비롯된 성향, 관련성을 가지고 결론 도출)
    
- 해로운 성명서
  - 현재의 우리 모두는 구조적 프로그래머이며, 여기에는 선태의 여지가 없다.
    - 제어흐름을 제약 없이 직접 전환할 수 있는 선택권 자체를 언어에서 미제공
  
- 기능적 분해
  - 구조적 프로그래밍으로 인해 거대한 문제 기술서를 받더라도 문제를 고수준의 기능들로 분해할 수 있다. 
  - 그리고 이들 각 기능은 다시 저수준의 함수들로 분해할 수 있고, 이러한 분해 과정을 끝없이 반복할 수 있다.
  - 이렇게 분해한 기능들은 구조적 프로그래밍의 제한된 제어 구조를 이용하여 표현할 수 있다.
  - 구조적 분석/구조적 설계 (유행)
    - 대규모 시스템을 모듈과 컴포넌트로 나눌 수 있고, 더 나아가 모듈과 컴포넌트는 입증할 수 있는 아주 작은 기능들로 세분화 가능
    
- 엄밀한 증명은 없었다.
  - 프로그램 관점에서 정리에 대한 유클리드 계층구조는 끝내 만들어지지 않았다.
  - 상당히 성공한 또 다른 전략으로는 과학적 방법이 있다.
  
- 과학이 구출하다.
  - 과학적 방법은 반증은 가능하지만 증명은 불가능하다.
  - 수학은 증명 가능한 서술이 참임을 입증하는 원리라고 볼 수 있다. 반면 과학은 증명 가능한 서술이 거짓임을 입증하는 원리라고 볼 수 있다.
  
- 테스트
  - "테스트는 버그가 있음을 보여줄 뿐, 버그가 없음을 보여줄 수는 없다."
    - 오히려 소프트웨어는 수학적인 시도가 아니라 과학과 같다.
      - 테스트를 통해 증명 가능한 세부 기능들이 거짓인지를 증명하려고 시도한다.(테스트가 실패한다면 참이라고 여긴다.)
    
- 결론
  - 구조적 프로그래밍이 오늘날까지 가치 있는 이유는 프로그래밍에서 반증 가능한 단위를 만들어 낼 수 있는 능력 때문이다.
  - 소프트웨어 아키텍트는 모듈, 컴포넌트, 서비스가 쉽게 반증 가능하도록(테스트 하기 쉽도록) 만들기 위해 분주히 노력해야 한다.
  
  
# 5장)객체 지향 프로그래밍
- 서론
  - 좋은 아키텍처를 만드는 일은 객체 지향 OO 설계 원칙을 이해하고 응용하는 데서 출발한다.
  - OO란 무엇인가?
    - 실제 세계를 모델링하는 새로운 방법 => 모호함
    - 캡슐화, 상속, 다형성 => OO의 본질을 얘기
    
- 캡슐화? (0점)
  - 캡슐화를 언급하는 이유는 데이터와 함수를 쉽고 효과적으로 캡슐화하는 방법을 OO 언어가 제공하기 떄문이다.
    - 데이터와 함수가 응집력 있게 구성된 집단을 서로 구분 짓는 선을 그을 수 있다.
    - 구분선 바깥에서는 데이터는 은닉되고, 일부 함수만이 외부에 노출된다.
      - 클래스의 private 멤버 데이터와 public 멤버 함수로 표현
  - 자바와 C#은 헤더와 구현체를 분리하는 방식을 모두 버렸고 이로인해 클래스 선언과 정의를 구분하는게 아얘 불가능해졌다.
    - 이 떄문에 OO가 강력한 캡슐화에 의존한다는 정의는 받아들이기 힘들다. (C언어에 비해 약화 되었다.)
    
- 상속? (0.5점)
  - 상속만큼은 OO언어가 확실히 제공했다?
    - OO 언어 전부터 C프로그래머는 우회적으로 이러한 방식을 구현했음
      - 하지만 상속만큼 편리한 방식은 아니고 다중 상속을 구현하기 어렵다.
    
- 다형성
  - 함수를 가리키는 포인터를 응용한 것이 다형성이다.
    - OO 언어는 다형성을 새롭게 만든건 아니지만, 다형성을 좀 더 안전하고 더욱 편리하게 사용할 수 있게 해준다.
    - OO의 다형성은 C처럼 포인터를 통해 사용하면서 실수할 수 있는 소지가 없다.
  - OO는 제어흐름을 간적접으로 전환하는 규칙을 부과한다.
    
  - 다형성이 가진 힘
    - 소스코드에 의존하지 않는다.
    - 플러그인 아키텍처는 이처럼 입출력 장치 독립성을 지원하기 위해 만들어졌고, 등장 이후 거의 모든 운영체제에서 구현되었다.
      -OO의 등장으로 언제 어디서든 플러그인 아키텍처를 적용할 수 있게 되었다.
      
  - 의존성 역전
    - P.48 (이미지) 다형성 전 메너키즘 : 고수준 -> 중간 수준 -> 저수준 호출
      - 제어 흐름은 시스템의 행위에 따라 결정되며, 소스 코드 의존성은 제어흐름에 따라 결정된다.
    - P.49 (이미지) ML1과 I 인터페이스 사이의 소스 코드 의존성(상호 관계)이 제어 흐름과는 반대이다.
      - 이는 의존성 역전이라고 부르며, 소프트웨어 아키텍트 관점에서 이러한 현상은 심오한 의미를 갖는다.
      - OO 언어가 다형성을 안전하고 편리하게 제공한다는 사실은 소스 코드 의존성을 어디에서든 역전시킬 수 있다는 뜻이다.
    - 의존성 역전을 통해무엇을 할 수 있을까?
      - 업무 규칙을 포함하는 컴포넌트는 UI와 데이터베이스를 포함하는 컴포넌트에 의존하지 않기 때문에 배포 독립성을 갖게 된다.
        - 시스템의 모듈을 독립적으로 배포할 수 있게 되면, 서로 다른 팀에서 각 모듈을 독립적으로 개발할 수 있다. 이것이 개발 독립성이다.
        
- 결 론
  - OO란 다형성을 이용하여 전체 시스템의 모든 소스 코드 의존성에 대한 절대적인 제어 권한을 획득할 수 있는 능력이다.
  - 고수준 정책을포함하는 모듈은 저수준의 세부사항을 포함하는 모듈에 대한 독립성을 보장할 수 있다.
      
      
# 6장)함수형 프로그래밍
- 서론
  - 이 패러다임에서 핵심이 되는 기반은 람다 계산법이다.
  
- 정수를 제곱하기
  - 클로저 vs 자바
    - 자바 프로그램은 가변 변수를 사용하는데, 가변 변수는 실행 중 상태가 변할 수 있다.
    - 클로저는 한 번 초기화되면 절대 변하지 않는다.
    
- 불변성과 아키텍처
  - 경합조건, 교착상태 조건, 동시 업데이트 문제가 모두 가변 변수로 인해 발생된다.
  - 아키텍트라면 동시성 문제에 지대한 관심을 가져야만 한다.
  
- 가변성이 분리
  - 불변 컴포넌트는 순수하게 함수형 방식으로만 처리되며 하나 이상의 다른 가변 컴포넌트와 서로 통신한다.
  - 상태 변경은 컴포넌트를 갖가지 동시성 문제에 노출하는 꼴이므로, 트랜잭션 메모리와 같은 실천법을 사용하여 가변 변수를 보호한다.
    - ex 자바 atomic) https://javaplant.tistory.com/23
  - 결론은 애플리케이션을 제대로 구조화 하려면 불변 컴포넌트와 가볍 컴포넌트 분리
    - 가변 변수들을 보호하는 적절한 수단이 뒷받침되야 한다.
    - 가능한 많은 처리를 불변 컴포넌트에서 하고 가변 컴포넌트에서는 많은 코드를 뺴내야 한다.
    
- 이벤트 소싱
  - 이벤트 소싱은 상태가 아닌 트랜잭션을 저장하자는 전략이다. 상태가 필요해지면 단순히 상태의 시작점부터 모든 트랜잭션을 처리한다.
    - 데이터 저장소에서 삭제되거나 변경되는 것이 하나도 없다.
    - 변경과 삭제가 전혀 발생하지 않기 때문에 동시성 이슈또한 없다.
    - 저장 공간과 처리 능력이 충분하면 애플리케이션이 완전한 불변성을 갖도록 만들 수 있다. (완전한 함수형)
  - 이벤트 소싱의 예) git, redis aof
  
- 결론
  - 구조적 프로그래밍은 제어흐름의 직접적인 전환에 부과되는 규율이다.
  - 객체 지향 프로그래밍은 제어흐름의 간접적인 전환에 부과되는 규율이다.
  - 함수형 프로그래밍은 변수 할당에 부과되는 규율이다.
  
  - 소프트웨어는 순차, 분기, 반복, 참조로 구성된다. (그 이상도 이하도 아니다.)
  
