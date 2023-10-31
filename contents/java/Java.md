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
정수형 byte(1), short(2), int(4), long(8) 
실수형 float(4), double(8)
문자형 char(2) 
논리형 boolean(1)이 있고, 해당 숫자만큼을 차지한다.

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