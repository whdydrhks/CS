# Java

<details>
<summary>❓ 자바의 특징을 설명해주세요.</summary>
<div markdown="1">

- Java는 객체지향 프로그래밍 언어입니다.
- 기본 자료형을 제외한 모든 요소들이 객체로 표현되고, 객체 지향 개념의 특징인 “캡슐화”, “상속”, “다형성”이 잘 적용된 언어입니다.

- 장점
  - JVM(자바 가상머신) 위에서 동작하기 때문에 OS에 독립적입니다.
  - Garbage Collector를 통한 자동적인 메모리 관리가 가능하다.
- 단점
  - JVM 위에서 동작하기 때문에 실행 속도가 상대적으로 느리다.
    - 다중 상속이나 타입에 엄격하며, 제약이 많다.

</div>
</details>

<details>
<summary>❓ JVM의 역할에 대해 설명해주세요.</summary>
<div markdown="1">

JVM은 스택 기반으로 동작하며, Java Byte Code를 OS에 맞게 해석 해주는 역할을 하고
가비지컬렉션을 통해 자동적인 메모리 관리를 해줍니다.

</div>
</details>

<details>
<summary>❓ Java의 컴파일 과정에 대해 설명해주세요.</summary>
<div markdown="1">

- 개발자가 java 파일을 생성한다.
- build를 한다.
- java compiler의 javac 명령어를 통해 바이트코드(.class)를 생성한다.
- Class Loader를 통해 JVM 메모리 내로 로드한다.
- 실행엔진을 통해 컴퓨터가 읽을 수 있는 기계어로 해석된다.
  (각 운영체제에 맞는 기계어)

</div>
</details>

<details>
<summary>❓ Java에서 제공하는 원시 타입들에 무엇이 있고, 각각 몇 byte를 차지하나요?</summary>
<div markdown="1">

- 정수형 byte(1), short(2), int(4), long(8)
- 실수형 float(4), double(8)
- 문자형 char(2)
- 논리형 boolean(1)이 있고, 해당 숫자만큼을 차지한다.

</div>
</details>

<details>
<summary>❓ 오버라이딩(Overriding)과 오버로딩(Overloading)에 대해 설명해주세요.</summary>
<div markdown="1">
<h4><span style="background-color: red; color: black;">오버라이딩(Overriding)</span></h4>은 상위 클래스에 있는 메소드를 하위 클래스에서 재정의 하는 것을 말하고,
<h4><span style="background-color: blue; color: black;">오버로딩(Overloading)</span></h4>은 매개변수의 개수나 타입을 다르게 하여 같은 이름의 메소드를 여러 개 정의하는 것을 말합니다.

</div>
</details>

<details>
<summary>❓ 객체지향 프로그래밍(OOP)에 대해 설명해주세요.</summary>
<div markdown="1">

우리가 실생활에서 쓰는 모든 것을 객체라 하며,객체 지향 프로그래밍은 프로그램 구현에 필요한 객체를 파악하고 상태와 행위를 가진 객체를 만들고 각각의 객체들의 역할이 무엇인지를 정의하여 객체들 간의 상호작용을 통해 프로그램을 만드는 것을 말합니다.<br><br>
즉, 기능이 아닌 <b>객체가 중심</b>이며, <b>"누가 어떤 일을 할 것인가?"</b> 가 핵심

특징으로는 <b><span style="color: #0080ff">캡슐화, 상속, 다형성, 추상화</span></b> 등이 있고,
모듈 재사용으로 확장 및 유지보수가 용이합니다.

</div>
</details>

<details>
<summary>❓ try-with-resources에 대해 설명해주세요.</summary>
<div markdown="1">

- try-with-resources는 try-catch-finally의 문제점을 보완하기 위해 나온 개념입니다.
- try( ... ) 안에 자원 객체를 전달하면, try블록이 끝나고 자동으로 자원 해제 해주는 기능을 말합니다.
- 따로 finally 구문이나 모든 catch 구문에 종료 처리를 하지 않아도 되는 장점이 있습니다.

</div>
</details>

<details>
  <summary>❓ 불변 객체가 무엇인지 설명하고 대표적인 Java의 예시를 설명해주세요.</summary>
  <div markdown="1">

- 불변 객체는 객체 생성 이후 내부의 상태가 변하지 않는 객체를 말합니다.
- Java에서는 필드가 원시 타입인 경우 `final` 키워드를 사용해 불변 객체를 만들 수 있고,
- 참조 타입일 경우엔 추가적인 작업이 필요하다.

    <details>
      <summary>❓ 참조 타입일 경우 추가적인 작업은 어떤게 있는지 설명해주세요.</summary>

      - 참조 타입은 대표적으로 다음을 참조할 수 있다.
        - 1) 객체 : 객체를 사용하는 필드의 참조 변수도 불변 객체로 변경해야 한다.
        - 2) 배열 : 배열을 받아 copy해서 저장하고, getter를 clone으로 반환하도록 하면 된다.
          - 배열을 그대로 참조하거나, 반환할 경우 외부에서 내부 값을 변경할 수 있음.
          - 때문에 clone을 반환해 외부에서 값을 변경 못하게 한다.
        - 3) List 등 : 배열과 마찬가지로 생성시 새로운 list를 만들어 값을 복사하도록 한다.
          - 배열과 리스트는 내부를 복사하여 전달하는데, 이를 방어적 복사(defensive-copy)라고 한다.

    </details>
    </div>
  </details>

<details>
<summary>❓ 불변 객체나 final을 굳이 사용해야 하는 이유가 무엇인가요?</summary>
<div markdown="1">

- Thread-Safe 하여 병렬 프로그래밍에 유용하며, 동기화를 고려하지 않아도 된다.
  - 공유 자원이 불변이기 때문에 항상 동일한 값을 반환하기 때문
- 실패 원자적인 메소드를 만들 수 있다.
  - 어떠한 예외가 발생되더라도 메소드 호출 전의 상태를 유지할 수 있어 예외 발생 전과
    똑같은 상태도 다음 로직 처리 가능
- 부수효과를 피해 오류를 최소화 할 수 있다.
  - 부수효과 : 변수의 값이 바뀌거나 객체의 필드 값을 설정하거나 예외나 오류가 발생하여
    실행이 중단되는 현상
- 메소드 호출 시 파라미터 값이 변하지 않는다는 것을 보장할 수 있다.
- 가비지 컬렉션 성능을 높일 수 있다. - 가비지 컬렉터가 스캔하는 객체의 수가 줄기 때문에 (GC 수행 시 지연시간도 줄어든다)
</div>
</details>

<details>
<summary>❓ <span style="color: #ff0000">추상 클래스</span>와 <span style="color: #0080ff">일반 클래스</span>의 차이점이 무엇인가요?</summary>
<div markdown="1">

<b>객체화 가능 여부</b> <br>
<span style="color: #ff0000">추상 클래스</span> <span style="color: #ff6666">불가</span><br>
<span style="color: #0080ff">일반 클래스</span> <span style="color: #66b2ff"> 가능</span>

</div>
</details>

<details>
<summary>❓ <span style="color: #ff0000">추상 클래스</span>와 <span style="color: #0080ff">인터페이스</span>를 설명해주시고, 차이에 대해 설명해주세요.</summary>
<div markdown="1">
<span style="color: #ff0000"></span>

- <span style="color: #ff0000">추상클래스</span>는 클래스 내 추상 메소드가 하나 이상 포함되거나 <span style="color: #ff6666">abstract</span>로 정의된 경우를 말하고,
- <span style="color: #0080ff">인터페이스</span>는 모든 메소드가 추상 메서드로만 이루어져 있는 것을 말한다.
- <span style="color: #00CC66">공통점</span>
  - new 연산자로 인스턴스 생성 불가능
  - 사용하기 위해서는 하위 클래스에서 확장/구현해야 한다.
- <span style="color: #ffff00">차이점</span>
  - <span style="color: #0080ff">인터페이스</span>는 그 인터페이스를 구현하는 모든 클래스에 대해 특정한 메소드가 반드시 존재하도록 강제함에 있고,
  - <span style="color: #ff0000">추상 클래스</span>는 상속받는 클래스들의 공통적인 로직을 추상화 시키고, 기능 확장을 위해 사용한다.
  - <span style="color: #ff0000">추상 클래스</span>는 <b>다중상속</b>이 <span style="color: #ff6666">불가능</span> 하지만, <span style="color: #0080ff">인터페이스</span>는 <b>다중상속</b>이 <span style="color: #66b2ff"> 가능</span>하다.
- 추상 클래스 : 클래스, 필드값 설정/메소드 내부 코딩 가능
- 인터페이스 : 클래스 X, 필드값 설정 불가(상수만 가능), 메소드 이름만 지정 가능

</div>
</details>

<details>
<summary>❓ 싱글톤 패턴에 대해 설명해주세요.</summary>
<div markdown="1">

- 싱글톤 패턴은 단 하나의 인스턴스를 생성해 사용하는 디자인 패턴입니다.
- 인스턴스가 1개만 존재해야 한다는 것을 보장하고 싶은 경우와
- 동일한 인스턴스를 자주 생성해야 하는 경우에 주로 사용합니다. (메모리 낭비 방지)

</div>
</details>

<details>
<summary>❓ 싱글톤 패턴의 대표적인 예시를 간단하게 설명해주세요.</summary>
<div markdown="1">

싱글톤 패턴의 대표적인 예시는 “**Spring Bean**” 입니다.

스프링의 빈 등록 방식은 기본적으로 싱글톤 스코프이고,

스프링 컨테이너는 모든 빈들을 싱글톤으로 관리합니다.

스프링은 요청할 때마다 새로운 객체를 생성해서 반환하는 기능도 제공한다.

(프로토타입 빈, @Scope(”prototype”))

</div>
</details>

<details>
<summary>❓ 가비지 컬렉션(Garbage Collection)에 대해 설명해주세요.</summary>
<div markdown="1">

가비지 컬렉션은 JVM의 메모리 관리 기법 중 하나로 시스템에서 동적으로 할당됐던 메모리 영역 중에서 필요없어진 메모리 영역을 회수하여 메모리를 관리해주는 기법입니다.

</div>
</details>

<details>
<summary>❓ 가비지 컬렉션 과정에 대해 설명해주세요.</summary>
<div markdown="1">

GC의 작업을 수행하기 위해 **JVM이 어플리케이션의 실행을 잠시 멈추고, GC를 실행하는 쓰레드를 제외한 모든 쓰레드들의 작업을 중단 후 (Stop The World 과정)**

**사용하지 않는 메모리를 제거-Mark and Sweep 과정**하고 작업이 재개됩니다.

++GC의 작업은 Young 영역에 대한 Minor GC와 Old 영역에 대한 Major GC로 구분됩니다.

</div>
</details>

<details>
<summary>❓ 객체지향의 설계원칙에 대해 설명해주세요.</summary>
<div markdown="1">

1. **SRP (Single responsibility principle)
   단일 책임 원칙** : 한 클래스는 하나의 책임만 가져야 한다.
2. **OCP (Open-closed principle)
   개방 폐쇄 원칙** : 확장에는 열려있고, 수정에는 닫혀있어야 한다.
3. **LSP (Liskov substitution principle)
   리스코프 치환 원칙** : 하위 타입은 항상 상위 타입을 대체 할 수 있어야 한다.
4. **ISP (Interface segregation principle)
   인터페이스 분리 원칙** : 인터페이스 내에 메소드는 최소한 일수록 좋다.
   (하나의 일반적인 인터페이스보다 여러 개의 구체적인 인터페이스가 낫다.)
   SRP와 같은 문제에 대한 두 가지 다른 해결책이다.
5. **DIP (Dependency inversion principle)
   의존관계 역전 원칙** : 구체적인 클래스보다 상위 클래스, 인터페이스, 추상클래스와 같이 변하지 않을 가능성이 높은 클래스와 관계를 맺어라.
   DIP 원칙을 따르는 가장 인기 있는 방법은 의존성 주입(DI)이다.

</div>
</details>

<details>
<summary>❓ 자바의 메모리 영역에 대해 설명해주세요.</summary>
<div markdown="1">

- 자바의 메모리 공간은 크게
  - **Method 영역**
  - **Stack 영역**
  - **Heap 영역**으로 구분되고,
- 데이터 타입에 따라 할당됩니다.
- **Method 영역**
  - **전역변수**와 **static 변수**를 저장한다.
  - **프로그램의 시작부터 종료까지 메모리에 남아있다.**
- **Stack 영역**
  - **지역변수**와 **매개변수** 데이터 값이 저장되는 공간이다.
  - **메소드가 호출될 때 메모리에 할당되고 종료되면 메모리가 해제된다.**
  - **LIFO(Last In First Out) 구조**를 갖고 변수에 새로운 데이터가 할당되면 이전 데이터는 지워진다.
- **Heap 영역**
  - **new 키워드로 생성되는 객체(인스턴스), 배열** 등이 저장된다.
  - **가비지 컬렉션(GC)에 의해 메모리가 관리**되어 진다.

</div>
</details>

<details>
<summary>❓ 각 메모리 영역이 할당되는 시점은 언제인가요?</summary>
<div markdown="1">

- Method 영역 : JVM이 동작해서 클래스가 로딩될 때 생성
- Stack 영역 : **컴파일 타임** 시 할당
- Heap 영역 : **런타임** 시 할당

**컴파일 타임** : 소스코드가 기계어로 변환되어 실행가능한 프로그램이 되는 과정

**런타임** : 컴파일 타임 이후 프로그램이 실행되는 때

</div>
</details>

<details>
<summary>❓ 클래스와 객체에 대해 설명해주세요.</summary>
<div markdown="1">

**클래스**는 객체를 만들어내기 위한 설계도 혹은 틀 이라고 할 수 있고, 객체를 생성하는데 사용한다.

**객체**는 설계도(클래스)를 기반으로 생성되며, 자신의 고유 이름과 상태, 행동을 갖는다.

여기서 상태는 필드(fields), 행동은 메소드(Method)라고 표현한다.

객체에 메모리가 할당되어 실제로 활용되는 실체는 ‘**인스턴스**’라고 부른다.

</div>
</details>

<details>
<summary>❓ 생성자(Constructor)에 대해 설명해주세요.</summary>
<div markdown="1">

생성자는 클래스와 같은 이름의 메소드로, 객체가 생성될 때 호출되는 메소드이다.

명시적으로 생성자를 만들지 않아도 default로 만들어지며, 생성자는 파라미터를 다르게 하여 오버로딩 할 수 있다.

</div>
</details>
