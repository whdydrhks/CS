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

<details>
<summary>❓ try-with-resources에 대해 설명해주세요.</summary>
<div markdown="1">
- try-with-resources는 try-catch-finally의 문제점을 보완하기 위해 나온 개념입니다.<br>
- try( ... ) 안에 자원 객체를 전달하면, try블록이 끝나고 자동으로 자원 해제 해주는 기능을 말합니다.<br>
- 따로 finally 구문이나 모든 catch 구문에 종료 처리를 하지 않아도 되는 장점이 있습니다.

</div>
</details>

<details>
  <summary>❓ 불변 객체가 무엇인지 설명하고 대표적인 Java의 예시를 설명해주세요.</summary>
  
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
</details>
