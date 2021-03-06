# 30장 데이터베이스는 세부사항이다.
### 서론
- 아키텍처 관점에서 데이터베이스는 엔티티가 아니다.
- 데이터베이스는 일개 소프트웨어일 뿐이다.

### 관계형 데이터베이스
- 관계형 데이터베이스는 데이터를 저장하고 접근하는데 탁월한 기술이었다.
  - 하지만 이 기술이 얼마나 뛰어나든, 유용하든, 아니면 수학적으로 견고하든, 결국은 그저 기술일 뿐이고 이는 세부사항임을 뜻한다.
- 데이터를 테이블에 행 단위로 배치한다는 자체는 아키텍처적으로 볼 때 전혀 중요하지 않다.
  - 애플리케이션의 유스케이스는 이러한 방식을 알아서는 안 되며 관여해서도 안된다.
  - 데이터가 테이블 구조를 가진다는 사실은 외부 원에 위치한 최하위 수준의 유틸리티 함수만 알아야 한다.
- 많은 데이터 접근 프레임워크가 테이블과 행이 객체 형태로 시스템에 돌아다니게 허용하는데 아키텍처적으로 잘못된 설계다
  - 이러면 유스케이스, 업무 규칙, 심지어는 UI조차도 관계형 데이터 구조에 결합되어 버린다.
  
### 데이터베이스 시스템은 왜 이렇게 널리 사용되는가?
- 데이터베이스가 소프트웨어 시스템과 소프트웨어 기업을 장악할 수 있었던 이유는 바로 **디스크** 때문이었다.
- 반 세기 동안 회전식 자기 디스크는 데이터 저장소의 중심에 있었다.
  - 디스크 기술은 계속 발전해 왔지만 치명적인 한가지 특성 (바로 느리다) 때문에 프로그래머를 괴롭혔다.
- 디스크 때문에 피해갈 수 없는 시간 지연을 완화하기 위해 색인, 캐시, 쿼리 계획 최적화가 필요해졌다.
  - 데이터 접근 및 관리 시스템이 필요했고, 두 가지 유형으로 분리되었다.
    - 파일 시스템
    - 관계형 데이터베이스 관리 시스템 (RDBMS)
- 파일 시스템
  - 파일 시스템은 문서(document) 기반이다.
  - 문서를 이름을 기준으로 저장하거나 조회할 때는 잘 동작하지만, 내용을 기준으로 검색할 때는 그리 크게 도움되지 않는다.
- 데이터베이스 시스템
  - 내용 기반이다.
  - 레코드가 서로 공유하는 일부 내용에 기반해서 다수의 레코드를 연관 짓는데 매우 탁월하나, 정형화되지 않은 문서를 저장하고 검색하는 데는 대체로 부적합하다.
  
- 이들 두 시스템은 데이터를 **디스크**에 체계화해서, 각 시스템에 특화된 방식으로 접근해야 할 때 가능한 한 효율적으로 데이터를 저장하고 검색할 수 있도록 한다.

### 디스크가 없다면 어떻게 될까?
- 디스크는 RAM으로 대체되고 있다. (테이프 드라이브, 플로피 드라, CD등 처럼 소멸중)
- 데이터가 RAM에 저장된다면 데이터를 어떻게 체계화할 것인가?
  - 이 데이터들은 리스트, 트리, 해시 테이블, 스택, 큐 혹은 무수히 많은 데이터 구조로 체계화할 것이며, 데이터에 접근할 때는 포인터나 참조를 사용할 것이다.
- 현재도 데이터를 RAM으로 읽은 후에 다루기 편리한 형태로 구조를 변경하고 있다.

### 세부사항
- 데이터베이스는 그저 메커니즘에 불과하며, 디스크 표면과 RAM 사이에서 데이터를 옮길 때 사용할 뿐이다.
- 아키텍처 관점에서 회전식 자기 디스크에 데이터가 있기만 한다면, 데이터가 어떤 형태인지 절대 신경 써서는 안 된다.

### 하지만 성능은?
- 성능은 아키텍처와 괸련된 관심사지만 데이터 저장소의 측면에서 성능은 완전히 캡슐화하여 업무 규칙과는 분리할 수 있는 관심사다.
- 데이터 저장소에서 데이터를 빠르게 넣고 뺄 수 있어야 하는 것은 맞지만, 이는 저수준의 관심사다.
- 성능은 시스템의 전반적인 아키텍처와는 아무런 관련이 없다.

### 개인적인 일화
- RAM vs RDBMS
  - 결국 고객의 요구사항으로 RDBMS를 도입했다. (마케팅의 승리)
- 그 시절로 다시 돌아간다면 한쪽에는 RDBMS를 붙이고, RDBMS에 대한 제한적이며 안정적인 몇 가지 데이터 접근 채널을 제공하는 동시에 시스템의 중심부에는 랜덤 액세스 파일을 유지

### 결론
- 데이터는 중요하지만, 데이터베이스는 세부사항이다.


# 31장 웹은 세부사항이다.
### 서론
- 1960년대 이래로 업계는 일련의 반복되는 진동을 겪어 왔고, 현재 웹은 이러한 진동의 맨 끝에 있을 뿐이다.
  - 반복되는 진동 : 모든 연산 능력을 중앙 서버에 두는 방식과 모든 연산 능력을 단말에 두는 방식

### 끝없이 반복하는 추
- 진동은 계속 반복되었고 앞으로도 우리는 연산 능력을 어디에 둘 알 수 없을 것이다.
- IT 역사 전체로 보면 웹은 아무것도 바꾸지 않았다. (수 많은 진동 중 하나에 불과하다.)
- 이 진동은 그저 핵심 업무 규칙의 중심에서 밀어내고 싶은 단기적인 문제일 뿐이다.
- Q사(재무시스템)의 사례에서 애플리케이션을 보호하기 위해서 업무 규칙을 UI로부터 분리 했어야 한다고 말하고 있다.
- A사(스마트폰)의 사례에서도 아키텍트가 UI와 업무 규칙을 서로 격리했기를 바란다고 말하고 있다.
  - 룩앤필
    - 소프트웨어 디자인에서 룩 앤드 필은 그래픽 사용자 인터페이스의 관점에서 쓰이며 색, 모양, 레이아웃, 글꼴(룩)뿐 아니라 단추, 상자, 메뉴와 같은 동적인 요소의 동작(필)을 수반하는 디자인의 측면을 이루고 있다

### 요약
- GUI는 세부사항이고 웹은 GUI이기 때문에 웹은 세부사항이다.
- 아키텍트라면 이러한 세부사항을 핵심 업무 로직에서 분리된 경계 바깥에 두어야 한다.
- 웹은 특이하고 다채롭기 때문에 장치 독립적인 아키텍처를 추구하는 일이 터무니 없다고 생각할 수 있다.
  - 어느 정도는 옳다. 애플리케이션과 GUI 상호작용은 '빈번하며' 상호작용 방식도 사용 중인 GUI 종류에 따라 차이가 매우 크다.
  - 하지만 UI와 애플리케이션 사이에는 추상화가 가능한 또 다른 경계가 존재한다.
    - 입력/출력 데이터 구조로 만들어서 유스케이스를 실행할 수 있는데 이 방식은 유스케이스가 장치 독립적인 방식으로 UI라는 **입출력 장치**를 동작시킨다고 간주할 수 있다.
  

### 결론
- 이러한 종류의 추상화는 만들기 쉽지 않고, 제대로 만들려면 수차례의 반복과정을 거쳐야 한다. 하지만 가능하다.


# 32장 프레임워크는 세부사항이다.
### 서론
- 프레임워크는 아키텍처가 될 수 없다.

### 프레임워크 제작자
- 프레임워크 제작자는 자신이나 자신의 동료들의 문제점을 알고 있고 그러한 문제들을 해결하기 위해 프레임워크를 만든다. (당신의 문제를 해결하기 위해서가 아니다.)
- 물론 당신의 문제는 프레임워크가 풀려는 문제와 꽤 많이 겹칠 것이다.
  - 겹치는 영역이 클수록 프레임워크는 실제로 더 유용

### 혼인 관계의 비대칭성
- 당신은 프레임워크를 위해 대단히 큰 헌신을 해야 하지만, 프레임워크 제작자는 당신을 위해 아무런 헌신도 하지 않는다.
- 프레임 워크 개발자는 프레임워크를 중심에 두고 우리의 아키텍처는 그 바깥을 감싸야 한다고 말한다.
  - 프레임워크의 기반 클래스에서 직접 파생하거나, 프레임워크의 기능을 업무 객체에 바로 임포트 해서 하용하라 권한다.
  - 당신의 애플리케이션이 가능하면 프레임워크에 공고하게 결합될 것을 강하게 역설한다.
- 모든 위험과 부담은 오롯이 당신이 감수할 뿐, 제작자가 감수하는 건 아무것도 없다.

### 위험 요인
- 위험 요인은 무엇인가?
  - 프레임워크 아키텍처는 그다지 깔끔하지 않은 경우가 많다.
    - 의존성 규칙을 위반하는 경향이 있다.
  - 프레임워크는 애플리케이션의 초기 기능을 만드는 데는 도움이 될 것이다.
    - 제품이 성숙해지면 제공하는 기능과 틀을 벗어나게 될 것이다.
  - 프레임워크는 당신에게 도움되지 않는 방향으로 진화할 수도 있다.
    - 사용 중이던 기능이 사라지거나 반영하기 힘든 형태로 변경될 수 있다.
  - 새롭고 더 나은 프레임워크가 등장해서 갈아타고 싶을 수도 있다.

### 해결책
- 프레임워크와 결합해서는 안 된다. 프레임워크는 아키텍처의 바깥쪽 원에 속하는 세부사항으로 취급하라
- 업무 객체를 만들 때 프레임워크가 자신의 기반 클래스로부터 파생하기를 요구하면 거절하고 대신 프락시(proxy)를 만들고, 업무 규칙에 플러그인할 수 있는 컴포넌트에 이들 프락시를 위치시켜라.
- 스프링을 사용할 때도 autowired 어노테이션이 업무 객체 도처에 산재해서는 안 된다. 업무 객체는 절대로 스프링에 대해서 몰라야 된다.
  - 업무 객체보다 메인(Main) 컴포넌트에서 스프링을 사용해서 의존성을 주입하는게 낫다. (메인은 가장 지저분한, 최저 수준의 컴포넌트)

### 이제 선언합니다
- 반드시 결합해야 되는 경우
  - C++, STL
  - 자바, 표준 라이브러리
- 애플리케이션과 프레임워크가 결합하면 모든 생애 주기를 함께 할 것이다.
  - 결코 가볍게 시작할 수 있는 관계가 아니다.

### 결론
- 가급적이면 프레임워크를 가능한 한 오랫동안 아키텍처 경계 너머에 두자.
