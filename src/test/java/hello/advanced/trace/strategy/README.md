### 전략 패턴

> 알고리즘 제품군을 정의하고, 각각을 캡슐화하여 상호 교환이 되게 만듭니다. <br>
> 전략을 사용하면 알고리즘을 사용하는 클라이언트와 독립적으로 알고리즘을 변경할 수 있습니다. <br> - GOF의 디자인 패턴

![스크린샷 2023-10-07 232825](https://github.com/jiyongYoon/study_springboot_advanced/assets/98104603/1f90dcf4-802f-4f65-9e67-a8c3e7ebae8d)
- 기존 `템플릿 메서드 패턴`은 `상속`을 사용하였기 때문에, 부모 코드가 변경되면 자식 코드들이 모두 변경을 받게 되었다.
- 하지만 `전략 패턴`의 경우 `인터페이스의 위임`을 사용하여 기존 문맥(`Context.execute()`) 메서드의 코드가 변경된다고 하더라도 `Strategy` 인터페이스를 구현하는 클래스들에는 전혀 영향을 주지 않는다.
> 즉, 의존하는 대상이 변경된 것이다.

---

### 템플릿 콜백 패턴

> **콜백이란?** <br>
> 프로그래밍에서 '콜백' 또는 '콜애프터 함수'는 다른 코드의 인수로서 넘겨주는 실행 가능한 코드를 말한다. <br>
> 콜백을 넘겨받는 코드는 이 콜백을 필요에 따라 즉시 실행할 수도 있고, 아니면 나중에 실행할 수도 있다. (위키백과)

스프링에서는 `ContextV2`와 같은 방식의 전략 패턴을 `템플릿 콜백 패턴`이라고 한다. <br>
`Context`가 템플릿 역할을 하고, `Strategy` 부분이 콜백으로 넘어온다고 생각하면 된다. <br>

_해당 패턴은 GOF 패턴이 아니며, 스프링 내부에서 이런 방식을 자주 사용하기 때문에, 스프링 안에서만 이렇게 부른다._ <br>
_`...Template`와 같은 클래스들이 '**템플릿 콜백 패턴**'으로 만들어져 있다고 생각하면 된다.