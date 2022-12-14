# spring
### 2021.12.30 완료
객체 지향 설계, 스프링의 핵심 원리 및 기능

### 강의 목차
1. 객체 지향 설계와 스프링
2. 스프링 핵심 원리 이해1 - 예제 만들기
3. 스프링 핵심 원리 이해2 - 객체 지향 원리 적용
4. 스프링 컨테이너와 스프링 빈
5. 싱글톤 컨테이너
6. 컴포넌트 스캔
7. 의존관계 자동 주입
8. 빈 생명주기 콜백
9. 빈 스코프


### SOLID 법칙이란?<hr/>
객체지향 설계는 긴 세월과 수많은 시행착오를 거치며 5가지 원칙이 정리되었다.<br/>
이것은 객체지향 설계의 5원칙이라고 하며, 앞글자를 따서 SOLID라고 한다.<br/>

* SPR(Single Responsibility Principle) : 단일 책임 원칙
* OCP(Open Closed Principle) : 개방 폐쇄 원칙
* LSP(Liskov Substitution Principle) : 리스코프 치환 원칙
* ISP(Interface Segregation Principle) : 인터페이스 분리 원칙
* DIP(Dependency Inversion Principle) : 의존 역전 원칙

이는 응집도는 높이고 결합도는 낮추자는 고전 원칙을 객체 지향의 관점에서 재정립한 것으로 볼 수 있다.<br/>

### SRP = 단일 책임 원칙<hr/>
클래스는 오직 하나의 책임을 가져야 한다.

#### SRP가 안지켜진 사례
* var
  + 하나의 속성이 여러 의미를 갖는 경우
  + 어떤 곳에서는 쓰고, 어떤 곳에선 안쓰는 속성이 있는 경우
* method
  + 분기처리를 위한 if문이 많을 경우<br/>


### OCP = 개방 폐쇄 원칙<hr/>
확장에 대해서는 열려 있어야 하지만 변경에 대해서는 닫혀 있어야 한다.<br/>
즉, 자신의 확장에는 열려있고, 주변의 변화에 대해서는 닫혀 있어야 한다는 것이다.<br/>
이것은 interface를 통해 구현하여 해결한다.<br/>

### LSP = 리스코프 치환 원칙<hr/>
서브 타입은 언제나 자신의 기반 타입으로 교체할 수 있어야 한다.<br/>
즉, 하위 클래스의 인스턴스는 상위형 객체 참조 변수에 대입해 상위 클래스의 인스턴스 역할을 수행하는 데 문제가 없어야 한다.<br/>
이것은 OOP 4대 특성의 상속, 인터페이스 원칙이 잘 지켜진 다면 LSP는 자동으로 잘 적용된 것이다.<br/>
(주로 조직도, 계층도 관점에서의 상속이 LSP를 위배하는 문제가 생긴다)<br/>

### ISP = 인터페이스 분리 원칙<hr/>
클라이언트는 자신이 사용하지 않는 메소드에 의존 관계를 맺으면 안된다.<br/>
ISP는 SRP와 비슷하지만 인터페이스를 통한 다른 해결책을 제안하고 있다. <br/>
예를들어 class 사람 implements 개발자 이면, 개발자 김모모 = new 사람() 을 통해 개발자 인터페이스의 메소드만을 사용하도록 제한하는 것이다.<br/>


### DIP = 의존 역전 원칙<hr/>
고차원 모듈은 저차원 모듈에 의존하면 안된다.<br/>
추상화된 것은 구체적인 것에 의존하면 안된다.<br/>
구체적인 것이 추상화된 것에 의존해야 한다.<br/>
자주 변경되는 클래스에 의존하면 안된다.<br/>
즉, 자신보다 변하기 쉬운 것에 의존하지 안되는 것을 의미한다.<br/>
해결방법은 OCP와 비슷하며 구체적인 class가 아닌, 인터페이스에 의존함으로써 DIP를 해결한다.<br/>
