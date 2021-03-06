# 5부 아키텍
# 15장 아키텍처란?
- 서 론
  - 소프트웨어 아키텍트
    - 최고의 프로그래머이며, 계속 프로그래밍 작업을 맡을뿐 아니라 동시에 생산성을 극대화할 수 있는 설계를 하도록 방향을 이끈다.
    - 프로그래밍 작업을 계속하는 이유는, 문제를 경험하지 않는다면 다른 프로그래머를 지원하는 작업을 제대로 수행할 수 없기 때문이다.

  - 소프트웨어 시스템의 아키텍처란 시스템을 구축했던 사람들이 만들어낸 시스템의 형태다.
    - 그 형태는 아키텍처 안에 담긴 소프트웨어 시스템이 쉽게 개발, 배포, 운영, 유지보수되도록 만들어진다.

  - 소프트웨어 아키텍처의 목표가 시스템을 제대로 동작하도록 만드는데 있다고 생각할 수 있지만, 이는 관련이 없다.
  - 아키텍처의 주된 목적은 시스템의 생명주기를 지원하는 것이다.
    - 아키텍처의 궁극적인 목표는 시스템의 수명과 관련된 비용은 최소화하고, 프로그래머의 생산성은 최대화하는데 있다.

- 개 발
  - 개발하기 힘든 시스템이라면 수명이 길지도 않고 건강하지도 않을 것이다.
    - 아키텍처는 개발팀이 시스템을 쉽게 개발할 수 있도록 뒷받침해야 한다.
  - 팀 구조가 다르면 아키텍처 관련 결정에서도 차이가 난다.
    - 팀이 적다면 잘 정의된 컴포넌트나 인터페이스가 없더라도 효율적으로 협력하여 모놀리틱 시스템을 개발할 수 있다.
      - 초기에 아키텍처 관련 제약들이 오히려 방해가 된다고 여길 수도 있다.
    - 팀이 분리되어 있다면 시스템을 신뢰할 수 있고 안정된 인터페이스를 갖춘, 잘 설계된 컴포넌트 단위로 분리해야 한다.
      - **팀별 단일 컴포넌트** 가 최적이진 않지만 일정에만 쫒겨 일한다면, 결국 이 아키텍처로 귀착될 것이다.
  
- 배 포
  - 배포 비용이 높을수록 시스템의 유용성은 떨어진다.
    - 아키텍처는 시스템을 단 한번에 쉽게 배포할 수 있도록 해야 한다.
  - 마이크로 서비스의 예
    - 너무 많은 마이크로서비스는 서로 연결하기 위해 설정하고 작동 순서를 결정하는 과정에서 오작동이 발생될 수 있다.
    - 아키텍트가 배포 문제를 초기에 고려했다면 더 적은 서비스를 사용하고, 컴포넌트를 하이브리드 형태로 융합하며, 종 더 통합된 도구를 사용해서 상호 연결을 관리했을 것이다.
    
- 운 영
  - 아키텍처는 개발, 배포, 유지보수에 미치는 영향보다 운영에 미치는 영향이 더 적다.
    - 적다는 것이지 시스템을 쉽게 운영하게 해주는 아키텍처가 바람직하지 않다는 것은 아니다.
  - 하드웨어는 값 싸고 인력은 비싸다.
    - 운영을 방해하는 아키텍처가 개발, 배포, 유지보수를 방해하는 아키텍처보다 비용이 덜 든다.
  - 좋은 소프트웨어 아키텍처는 시스템을 운영하는데 필요한 요구도 알려준다.
    - 유스케이스, 기능, 시스템의 필수 행위를 일급 엔티티로 격상 시키고, 개발자들에게 주요 목표로 인식되도록 한다.
      - => 시스템 이해도가 높아지며, 따라서 개발과 유지보수에 큰 도움이 된다.

- 유지보수
  - 소프트웨어 시스템에서 비용이 가장 많이 든다.
  - 유지보수의 가장 큰 비용은 탐사와 이로 인한 위험부담에 있다.
    - 탐사란 기존 소프트웨어에 기능을 추가하거나 수정 시, 어디를 고치는 것이 최선인지 그리고 어떤 전략을 쓰는게 최적일지 결정하는 비용. 
    - 여기에는 변경사항을 반영 시, 결함에 대한 위험 부담도 추가된다.
  - 주의를 기울여 신중하게 아키텍처를 만들면 이 비용을 크게 줄일 수 있다.
    - 시스템을 컴포넌트로 분리하고, 안정된 인터페이스를 두어 서로 격리.
  
- 선택사항 열어 두기
  - 소프트웨어는 행위적 가치와 구조적 가치를 지닌다. (소프트웨어를 부드럽게 만들기 때문에 구조적 가치가 더 중요)
    - 2장) 행위는 기능개발하고, 버그 수정하고 / 구조는 아키텍처 (행위를 빠르고 쉽게 변경할 수 있도록)
  - 소프트웨어를 부드럽게 유지하는 방법은 선택사항을 가능한 많이, 그리고 가능한 오랫동안 열어 두는 것이다.
    - 여기서 말하는 열어둬야할 선택사항은 바로 **중요치 않은 세부사항** 이다.
  - 모든 소프트웨어 시스템은 **정책**과 **세부사항**으로 분해할 수 있다.
    - 정책이란 시스템의 진정한 가치가 살아 있는 곳 (정책 요소는 모든 업무 규칙과 업무 절차를 구체화한다.)
    - 세부사항은 사람, 외부 시스템, 프로그래머가 정책과 소통할 때 필요한 요소 (정책이 가진 행위는 영향을 미치지 않음)
      - ex) 입출력 장치, 데이터베이스, 웹 시스템, 서버, 프레임워크, 통신 프로토콜 등 (고수준을 참조 하는 저수준)
  - 아키텍트의 목표는 시스템에서 정책을 가장 핵심적인 요소로 식별하고, 동시에 세부사항은 정책에 무관하게 만들 수 있는 형태의 시스템을 구축
    - 개발 초기에 데이터베이스 시스템 선택할 필요가 없음
    - 개발 초기에 웹 서버를 선택할 필요가 없음
    - 개발 초기에 REST를 적용할 필요가 없음
    - 개발 초기에 의존성 주입 프레임워크를 적용할 필요가 없음
      - 결론 : 세부사항에 몰두하지 않은 채 고수준의 정책을 만들 수 있다면, 이러한 세부사항에 대한 결정을 연기할 수 있다.
  - 선택사항을 더 오랫동안 열어 둘 수 있다면 더 많은 실험을 해볼 수 있고 더 많은 것을 시도할 수 있다.
  - **좋은 아키텍트는 결정되지 않은 사항의 수를 최대화한다.**
    
- 장치 독립성
  - 저자가 잘못한 수많은 실수사례
    - 코드를 입출력 장치와 직접 결합한 사례 (장치 종속적)
      - 카드 판독기에서 카드를 읽어야 할 경우 카드 판독기와 직접 상호작용하도록 코드 작성 / 천공 카드에 구멍을 뚫어야 할 경우에도 카드 천공기를 직접 조작하는 코드 작성
        - 큰 규모의 천공카드 뭉치는 관리하기 어렵고 잃어 버리거나 찢어지거나 등 여러가지 문제 대두
      - 자기 테이프를 이용해서 문제 해결할 수 있지만 프로그램을 다시 작성해야 되서 너무 큰 작업
    - 결국 추상화를 통해 장치 독립성 생각해냄 (개방 폐쇄 원칙의 탄생 순간)
  
- 광고 우편
  - 정책을 세부사항으로 부터 분리했던 사례 (광고 우편)
    - 라인 프린터 (비쌈) => 자기 테이프를 사용해서 오프라인 프린터 다섯대랑 연결 (가능했던 이유는 운영체제의 입출력 추상화를 사용해서 작성되어 있었음)
    - 장치 독립성으로 인해 테스트 시에는 라인 프린터 사용하다 실제 인쇄 시에는 자기 테이프에 인쇄 하도록
  - 위 사례는 정책을 세부사항으로 부터 분리 했기 때문에 가능했다.
    - 여기서 정책은 이름과 주소 레코드에 대한 서식
    - 세부사항은 장치 (라인 프린터 대신 자기 테이프)
        
- 물리적 주소 할당
  - 고수준의 정책이 디스크의 물리적 구조로부터 독립되도록 수정한 사례
  
- 결 론
  - 좋은 아키텍트는 세부사항을 정책으로부터 신중하게 가려내고, 정책이 세부사항과 결합되지 않도록 엄격하게 분리
  - 좋은 아키텍트는 세부사항에 대한 결정을 가능한 오랫동안 미룰 수 있는 방향으로 정책 설계
  
# 16장 독립성
- 서 론
  - 좋은 아키텍처는 다음을 지원해야 한다.
    - 시스템의 유스케이스
    - 시스템의 운영
    - 시스템의 개발
    - 시스템의 배포
    
- 유스케이스
  - 참고) 유스 케이스(Use case)는 UML(통합 모델링 언어)의 행위자(액터)와 액터가 요구하여 시스템이 수행하는 일의 목표이다.
  
  - 시스템의 아키텍처는 시스템의 의도를 지원해야 한다.
    - ex) 장바구니 애플리케이션이라면 장바구니 관련 유스케이스를 지원해야 한다.
  - 아키텍처는 반드시 유스케이스를 지원해야 한다. (최우선)
  - 아키텍처는 시스템의 행위에 큰 영향을 주지 않는다.
    - 하지만 좋은 아키텍처가 행위를 지원하기 위해 할 수 있는 일 중 가장 중요한 사항은 행위를 명확히 하고 외부로 드러내며, 이를 통해 시스템이 지닌 의도를 아키텍처 수준에서 알아 볼 수 있게 만드는 것
      - 행위는 일급 요소이며 시스템의 최상위 수준에서 알아볼 수 있기 때문에 개발자들이 금방 찾을 수 있다. (일급 요소가 의미하는것은 뭘까??....)

- 운 영
  - 시스템의 운영 지원 관점에서 볼 때 아키텍처는 더 실질적이며 덜 피상적인 역할을 맡는다. (피상적 : 본질보다는 겉으로 보이는 현상)
  - 뛰어난 아키텍트라면 열어 두어야 하는 선택사항 중의 하나다.
    - 시스템의 처리 요소를 일련의 작은 서비스들로 배열하여, 서로 다른 서버에서 병렬로 실행 하는 시스템
    - 경량의 수 많은 스레드가 단일 프로세스에서 같은 주소 공간을 공유하도록 처리하는 시스템
    - 독립된 주소 공간에서 실행되는 소수의 프로세스만으로 충분한 시스템
    - 단일 프로세스에서 실행되는 단순한 모놀리틱 프로그램 정도의 시스템
  - 모놀리틱 구조인 경우 다중 프로세스, 다중 스레드, 마이크로서비스 형태가 필요할때 개선하기 어렵다.
  - 컴포넌트를 적절히 격리하여 유지한 경우 요구 사항이 바뀌더라도 스레드, 프로세스, 서비스로 구성된 기술로 전환하는 일이 쉬워질 것이다.
    
- 개 발
  - 아키텍처는 개발환경을 지원하는데 있어 핵심적인 역할을 수행한다.
  - 콘 웨이 법칙
    - 시스템을 설계하는 조직이라면 어디든지 그 조직의 의사소통 구조와 동일한 구조의 설계를 만들어 낼 것이다.
  - 예를 들어 많은 팀으로 구성되며 관심사가 다양한 조직이라면 각 팀이 독립적으로 행동하기 편한 아키텍처를 확보해서 서로 방해하지 않도록 해야 한다.
    - 독립적 개발 가능한 컴포넌트 단위로 시스템 분할

- 배 포
  - 아키텍처는 배포 용이성을 결정하는데 중요한 역할을 한다.
    - 목표는 즉각적인 배포다.
  - 좋은 아키텍처라면 시스템이 빌드된 후 즉각 배포할 수 있도록 지원해야 한다.
    - 이런 아키텍처를 만들려면 시스템을 컴포넌트 단위로 적절하게 분할하고 격리시켜야 한다.
    
- 선택사항 열어 놓기
  - 좋은 아키텍처는 컴포넌트 구조와 관련된 관심사들 사이에서 균형을 맞추고, 각 관심사 모두를 만족시킨다.
    - 하지만 현실에서는 이러한 균형을 잡기가 매우 어렵다.
      - 모든 유스케이스를 알 수 없다.
      - 운영하는데 따르는 제약사항, 팀 구조, 배포 요구사항도 알지 못한다.
      - 이러한 사항들을 알고 있더라도, 시스템이 생명주기의 단계를 하나씩 거쳐감에 따라 이 사항들도 반드시 변해간다.
  - 좋은 아키텍처는 선택사항을 열어 둠으로써, 향후 시스템에 변경이 필요할 때 어떤 방향으로든 쉽게 변경할 수 있도록 한다. (세부사항에 대한 결정을 가능한 오랫동안 미룰 수 있는 방향으로 정책 설계)
 
- 계층 결합 분리 (UI, 업무, 데이터)
  - 아키텍트는 유스케이스 전부를 알지는 못하지만 시스템의 기본적인 의도는 분명히 알고 있다.
  - 아키텍트는 단일 책임 원칙과 공통 폐쇄 원칙을 적용하여, 그 의도의 맥락에 따라서 다른 이유로 변경되는 것들을 분리하고, 동일한 이유로 변경되는 것들은 묶는다.
  - 서로 다른 이유로 변경되는 이유는?
    - 사용자 인터페이스 변경되는 이유는 업무 규칙과는 관련 없음 (UI의 변경은 비즈니스 로직과 관계 없음)
    - 유스케이스가 두 가지 요소를 모두 포함한다면 뛰어난 아키텍트는 UI 부분과 업무 규칙 부분을 서로 분리하고자 할 것이다. (독립적으로 변경)
  - 업무 규칙은 그 자체가 애플리케이션과 밀접한 관련이 있거나, 혹은 더 범용적일 수도 있다.
    - ex) 애플리케이션 자체 업무 규칙과 업무 도메인에 더 밀접하게 연관된 업무 규칙
      - 이 둘은 다른 속도로로 다른 이유로 변경될 것이기 때문에 서로 분리하고 독립적으로 변경할 수 있도록 만들어야 됨
  - 데이터베이스, 쿼리 언어, 스키마 조차 세부사항이며, 업무 규칙이나 UI와는 관련 없다. (독립적으로 변경)
  - 수평적 계층으로 분리 하는 방법
    - ex) UI, 애플리케이션에 특화된 업무, 애플리케이션과 독립적인 업무, 데이터베이스 등
  
- 유스케이스 결합 분리
  - 유스케이스 자체도 서로 다른 이유로 변경된다.
  - 유스케이스는 시스템을 분할하는 매우 자연스러운 방법이다.
    - ex) 주문 추가, 주문 삭제
  - 우리는 시스템을 수평적 계층으로 분할하면서 동시에 해당 계층을 가로지르는 얇은 수직적인 유스케이스로 시스템을 분할할 수 있다.
      - ex) 161P 그림
        - AOP 개념과 비슷 (횡단 관심사)
  - 시스템에서 서로 다른 이유로 변경되는 요소들의 결합을 분리하면 기존 요소에 지장을 주지 않고도 새로운 유스케이스를 계속 추가 할 수 있음
    - UI와 데이터를 서로 묶어서 각 유스케이스가 UI와 데이터베이스의 서로 다른 관점을 사용하게 되면, 새로운 유스케이스를 추가하더라도 기존 유스케이스에 영향이 거의 없다.
  - 느낀점 : 횡단 관심사라 볼 수 있나? 공통적인 기능이 아닌 교차로 인해 여러 기능이 발생되는데...
      
- 결합 분리 모드
  - 결합 분리 시 운영 관점에서는 어떤 의미가 있을까?
  - 유스케이스에서 서로 다른 관점이 분리되었다면, 높은 처리량을 보장해야 하는 유스케이스와 낮은 처리량으로도 충분한 유스케이스는 이미 분리되어 있을 가능성이 높다.
    - UI와 데이터베이스가 업무 규칙과 분리되어 있다면 업무 규칙과 다른 서버에서 실행될 수도 있다.
  - 간단히 말해 유스케이스를 위해 수행하는 결합 분리는 운영에도 도움이 된다.
    - 주의할 점은 반드시 독립적인 서비스가 되어야 하고, 네트워크를 통해 통신해야 된다. (동일한 주소 공간에서 상주 X)
  - 서비스, MSA, SOA 등의 예기가 나오지만 여기서 하고 싶은 얘기는 떄떄로 컴포넌트를 서비스 수준까지도 분리해야 된다.
  - 좋은 아키텍처는 선택권을 열어 두는데 결합 분리 모드는 이러한 선택지중 하나다.
  
- 개발 독립성
  - 컴포넌트가 완전히 분리되면 팀 사이의 간섭은 줄어든다.
    - ex) UI팀과 업무 규칙팀
    - ex) addOrder, deleteOrder (유스케이스)
    
- 배포 독립성 
  - 유스케이스와 계층의 결합이 분리되면 배포 측면에서도 고도의 유연성이 생긴다.
    - 운영중인 시스템에서 계층과 유스케이스를 교체할 수 있다. (jar 추가)
    
- 중 복
  - 1) 진짜 중복
    - 인스턴스 변경 시, 동일한 변경을 그 인스턴스 복사본에 반드시 적용
  - 2) 거짓 중복 (우발적 중복)
    - 중복으로 보이는 두 코드 영역이 서로 다른 속도와 다른 이유로 변경된다면 이 두코드는 진짜 중복이 아니다.
      - 현재는 중복으로 보이나 몇 년후에는 두 코드가 매우 다르게 보인다.
  - 유스케이스에서 화면 구조가 매우 비슷하다면 우발적 중복일 가능성이 높다.
    - 시간이 지나면 두 화면은 서로 다른 방향으로 분기하며, 결국 다른 모습을 가질 가능성이 높다.
  - 유스케이스 수직분리 시
    - 유스케이스가 서로 비슷한 화면, 비슷한 알고리즘, 비슷한 데이터베이스 스키마를 가지기 때문에 통합하고 싶다는 유혹을 받게 된다.
  - 계층 수평분리 시
    - 레코드를 그대로 UI로 보내고 싶은 유혹을 조심하라. 뷰 모델을 별도로 만드는 일은 별로 노력이 들지 않고 계층간 결합을 분리하는데도 도움이 된다.
    
- 결합 분리 모드(다시)
  - 소스 수준 분리 모드
    - 소스 코드 모듈 사이의 의존성 제어.
    - 하나의 모듈이 변하더라도 다른 모듈은 변경하거나 재컴파일 하지 않도록 함.
    - 모든 컴포넌트가 같은 주소 공간에서 실행되고 서로 통신할 떄는 간단한 함수 호출 이용 (모놀리틱 구조)
  - 배포 수준 분리 모드
    - jar 파일, DLL, 공유 라이브러리와 같이 배포 가능한 단위들 사이의 의존성을 제어.
    - 한 모듈의 소스 코드가 변하더라도 다른 모듈을 재빌드하거나 재배포하지 도록 만들 수 있음
    - 결합이 분리된 컴포넌트가 jar파일, Gem파일, DLL과 같이 독립적으로 배포할 수 있는 단위로 분할
  - 서비스 수준 분리 모드
    - 의존하는 수준을 데이터 구조 단위까지 낮출 수 있고, 순전히 네트워크 패킷을 통해서만 통신하도록 할 수 있다.
    - 모든 실행 가능한 단위는 소스와 바이너리 변경에 대해 서로 완전희 독립적이다. (서비스 또는 마이크로서비스)
  - 어떤 모드가 가장 좋은가?
    - 초기에는 알기 힘들고 프로젝트가 성숙해갈수록 최적인 모드가 달라진다.
  - 좋은 아키텍처는 시스템이 모노리틱 구조로 태어나서 단일 파일로 배포되더라도, 이후에는 독립적인 서비스나 마이크로서비스 수준까지 성장할 수 있도록 만들어져야 한다.
    - 좋은 아키텍처라면 역방향의 형태인 모놀리틱 구조로 되돌릴 수도 있어야 한다.
    
- 결 론
  - 시스템의 결합 분리 모드는 시간이 지나면서 바뀌기 쉬우며, 뛰어난 아키텍트라면 이러한 변경을 예측하여 큰 무리 없이 반영할 수 있도록 해야 한다.
  
# 17장 경계: 선 긋기
- 서 론
  - 소프트웨어 아키텍처는 선을 긋는 기술이며, 이러한 선을 경계라고 부른다.
  - 아키텍트의 목표는 필요한 시스템을 만들고 유지하는데 드는 인적 자원을 최소화하는 것이다.
    - 인적 자원의 효율을 떨어뜨리는 요인은 결합(coupling) 이다.
  
- 두 가지 슬픈 이야기
  - P회사의 사례 (너무 이른 결정에는 위험이 따른다는 경고)
    - 1) 1980년대 모노리틱 테스크톱 애플리케이션을 만들어 큰 성공을 거둠
    - 2) 1990년대 후반이 되자 웹이 대새 되었고 웹 버전으로 변환하는 프로젝트 착수
    - 3) 3(GUI, 미들웨어, 데이터베이스) 티어로 구성된 리치 아키텍처를 채택 (너무 이른 선택)
    - 4) 티어간 통신이 필요했고, 결국 리치 시스템이 구성됨
    - 5) 단일 장비에서 실행함에도 불구하고, 직렬화, 마샬링과 언마샬링, 메시지 구성 및 파싱, 소켓 통신등을 단일 머신에서 실행하는 일을 지속
    - 6) 결국 서버 팜을 필요로 하는 시스템을 한 번도 판매하지 못함.
      - 결론 : 아키텍트가 너무 이르게 결정을 내림으로써 개발 비용을 엄청나게 가중시킨 사례
      
  - W회사의 사례
    - 1) 아키텍트를 고용해서 소프트웨어 작업을 통제하고자 함.
    - 2) 서비스 지향 아키텍처(SOA)가 필요하다고 느낌
      - 모든 객체들로 구성된 거대한 도메인 모델을 생성했고, 이들 도메인 객체를 관리하기 위한 서비스들의 묶음을 설계했다.
    - 3) 데이터를 전달하기위해 가짜 데이터를 채워서 사용했고 테스트를 위해서는 필요한 서비들을 하나씩 구동시켰다. (큐에 의한 전달 지연도 발생)
    - 4) 새로운 기능 추가 시, WSDL (서비스 메시지 포멧, 프로토콜 등) 을 변경해야 하며, 영향 받는 부분을 다시 배포해야 함.
      - 결론 : SOA를 너무 일찍 채택해서 엄청난 양의 인적 시간에 따른 비용이 발생되었다.
      
- FitNesse (성공사례)
  - 1) FIT 도구를 기반으로 하는 간단한 위키 페이지를 만들려함
  - 2) maven 등장 전이라서 jar 파일을 둘 이상 다운로드 하도록 만들어서는 안된다는 원칙을 세움 (다운로드 후 바로 실행)
  - 3) 초기 결정 중 하나는 웹 서버를 직접 작성하자 였다.
    - 기본 뼈대만 갖춘 웹서버는 단순한 단일 소프트웨어이기 때문에 구현이 간단했고, 사용할 웹 프레임워크에 대한 결정을 나중으로 연기할 수 있었다. 데이터베이스에 대한 고민도 마찬가지 였다.
  - 4) 데이터 접근 메서드들을 WikiPage 라는 인터페이스(페이지 찾고, 데이터 가지고 오고, 저장) 에 두어 실제 기능은 단순 스텁(stub)으로 만들었다.
  - 5) 실제 데이터가 필요 할때 WikiPage의 파생 클래스 InMemoryPage를 RAM에 유지되는 해시테이블 기반으로 만들었다.
  - 6) 영속성을 구현해야 되는 시점에는 MySQL 대신 파일 기반으로 저장
  - 7) 결국 고객의 요청으로 MySQL도 지원 하기로 했고 WikiPage(인터페이스) 기반으로 하루만에 MySqlWikiPage 라는 파생 클래스를 만들어 동작하게 만듬 (결국 사용안함)
    - 결론 : 개발 초기에 업무 규칙과 데이터베이스 사이에 경계선을 그어서 데이터 베이스에 대한 결정을 최대한 지연 시켰고 새 데이터 베이스 추가 시에는 방해도 되지 않았다.
      - 경계선을 긋는 행위는 결정을 늦추고 연기하는데 도움이 되었고 궁극적으로는 시간을 엄청나게 절약해주었다.
      
- 어떻게 선을 그을까? 그리고 언제 그을까?
  - 관련이 있는 것과 없는 것 사이에 선을 긋는다.
    - GUI, 업무규칙, 데이터베이스 는 서로간에 관련이 없기 떄문에 선을 긋는다.
  - 데이터베이스가 업무 규칙과 연관되었다고 생각할 수 있지만 업무 규칙이 간접적으로 사용할 수 있는 도구일 뿐이다.
    - 업무 규칙이 알아야 할 것은 데이터를 가져오고 저장할 때 사용할 수 있는 함수 집합이 있다는 정도
  - <img width="449" src="https://user-images.githubusercontent.com/7076334/97996458-2352fb80-1e2b-11eb-8210-99333cb72134.png">
  
    - DatabaseAccess 출발하는 두 화살표는 클래스로부터 바깥쪽으로 향한다. 즉 DatabaseAccess가 존재한다는 사실을 알고 있는 클래스는 없다.
  
  - <img width="437" src="https://user-images.githubusercontent.com/7076334/97997437-4af69380-1e2c-11eb-830e-d84c4a33813d.png">
  
    - Database는 BusinessRules 없이는 존재할 수 없다.
    - 이 때문에 BusinessRules에서는 어떤 종류의 데이터베이스도 사용할 수 있다.
    - 이 같은 사실은 데이터베이스에 대한 결정은 연기할 수 있으며, 결정하기에 앞서 업무 규칙을 먼저 작성하고 테스트하는데 집중할 수 있다.
    
- 입력과 출력은?
  - 개발자와 고객은 종종 처음부터 GUI가 동작하는 모습을 봐야 된다고 생각하지만 사실 입력과 출력은 중요하지 않다.
  - 시스템 행위를 입출력이 지닌 행위적 측면으로 생각하는 경향이 있다.
    - ex) 비디오 게임에서 사용자 경험은 인터페이스에 좌우된다. (화면, 마우스 버튼, 음향 등)
    - 인터페이스 뒤에는 인터페이스를 조작하는 모델(데이터 구조와 함수로 구성된 정교한 집합) 이 존재한다.
    - 사실 모델은 인터페이스를 전혀 필요로 하지 않는다. (화면에 출력되지 않아도 모델은 수행된다.) 중요한건 업무 규칙이다.
    
    - <img width="435" src="https://user-images.githubusercontent.com/7076334/97997449-4df18400-1e2c-11eb-846e-9206cc7d2c30.png">
    
      - 관련성이 낮은 컴포넌트가(저수준) 관련성이 높은 컴포넌트에 의존한다.(고수준)
      - GUI는 다른 종류의 인터페이스로 얼마든지 교체할 수 있다.
      
- 플러그인 아키텍처
  - 소프트웨어 개발 기술의 역사는 플러그인을 손쉽게 생성하여, 확장 가능하며 유지보수가 쉬운 시스템 아키텍처를 확립할 수 있게 만드는 방법에 대한 이야기다.
  - 다양한 형태로 구현될 수 있는 컴포넌트로부터 핵심적인 업무 규칙은 분리되어 있고 독립적인다.
  
  - <img width="454"  src="https://user-images.githubusercontent.com/7076334/97999635-e8eb5d80-1e2e-11eb-8485-5782f31c4065.png">
  
    - 사용자 인터페이스(GUI)는 웹이 될수도 있고 클라이언트/서버 기반이거나 SOA나 콘솔 기반등 다양한 사용자 인터페이스 기술 가능
    - 데이터베이스도 SQL 데이터베이스, NoSQL 데이터베이스, 파일 시스템 기반 등 여러가지로 대체할 수 있다.
    
- 플러그인에 대한 논의
  - 웹 페이지의 포멧을 변경하거나 데이터베이스 스키마를 변경하더라도 업무 규칙은 깨지지 않기를 바란다.
  - 시스템에서 한 부분이 변경되더라도 관련 없는 나머지 부분이 망가지길 원치 않는다.
  - 시스템 플러그인 아키텍처로 배치함으로써 변경이 전파될 수 없는 방화벽을 생성할 수 있다.
  - 경계는 변경의 축이 있는 지점에 그어진다. (축을 기점으로 변경되는 속도와 이유가 다르다.)
    - 단일 책임 원칙에 해당하며, 이는 어디에 경계를 그어야 할지 알려 준다.
  
- 결 론
  - 경계선을 그리기 위해서
    - 1) 컴포넌트 단위로 분할
    - 2) 컴포넌트 소스를 배치 (의존성 화살표 저수준 세부사항 -> 고수준 추상화)
