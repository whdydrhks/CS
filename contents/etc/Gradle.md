## Gradle이란 ❓
2012년에 출시된 Groovy를 기반으로 한 오픈소스 빌드 도구로,

거의 모든 타입의 소프트웨어를 빌드할 수 있는 **빌드 자동화 시스템**이다.

## 빌드란 ❓
소스 코드를 컴파일, 테스트, 정적분석 등을 실행하여 실행 가능한 어플리케이션으로 만들어주는 과정

**다양한 라이브러리의 등장** => <span style="color:red">문제점 발생!</span>
- 라이브러리를 다운로드 및 추가하는 번거로움
- 개발자들 간의 버전관리 어려움
- 다운받은  jar 파일의 보안 위험

**이를 <span style="color:blue">해결</span>하는 도구** => <span style="color:blue">빌드 도구</span>
- 계속해서 늘어나는 라이브러리를 자동 추가 및 관리
- 프로젝트를 진행하여 라이브러리의 버전을 쉽게 동기화

## Groovy란 ❓
**JVM 상에서 실행되는 스크립트 언어
Java와 유사한 문법 구조를 가지며, 호환성이 아주 좋다.**<br>
Gradle의 기반이 된다.

## Gradle의 <span style="color:#009999">장점</span> ❓
**✅ 프로젝트를 설정 주입(Configuration Injection) 방식으로 정의 ⇒ 재사용에 유리함**
- 필요한 정보가 있다는 그것을 프로젝트에 주입한다는 의미
- Maven의 상속 구조보다 재사용에 용이함
- 프로젝트의 조건을 체크할 수 있어서 프로젝트별로 주입되는 설정을 다르게 할 수 있다.

**✅ 멀티 프로젝트 빌드 ⇒ 여러 프로젝트를 사용할 수 있다**
- 하나의 repository 내에 여러개의 하위 프로젝트를 구성할 수 있다.
- Ex) 관리자 서버, 유저 서버를 분리해서 gradle을 따로 두어 중복을 피할 수 있다.
    아래 처럼 각각에 맞는 gradle 설정
- 👨🏻‍💻📁 - 👨🏻‍💻🐘
- 👩🏻‍💻📁 - 👩🏻‍💻🐘

**✅ 빌드 속도가 빠름 ⇒ 최적화에 유리**
- 점진적 빌드(Incremental Builds)
    - 마지막 빌드 호출 이후에 task의 변경 여부를 확인하여 변경되지 않았다면 빌드를 실행하지 않는다.
- 빌드 캐시(Build Cache)
    - 두 개 이상의 빌드가 돌아가고, 하나의 빌드에서 사용되는 파일들이 다른 빌드들에 사용된다면 Gradle은 빌드 캐시를 이용해 이전 빌드의 결과물을 다른 빌드에서 사용할 수 있다.
    - 다시 빌드하지 않아도 되므로 빌드 시간이 줄어들게 된다.
- 데몬 프로세스
    - 데몬 프로세스 : 서비스의 요청에 응답하기 위해 오랫동안 살아있는 프로세스
    - Gradle의 데몬 프로세스는 메모리 상에 빌드 결과물을 보관
    - 이로 인해, 한 번 빌드된 프로젝트는 다음 빌드에서 매우 적은 시간만 소요된다.

### Gradle의 dependencies 활용
**api : 내부 의존성을 컴파일과 런타임 모두에 보이는 API 의존성**<br>
**implementation : 내부 의존성을 런다임에만 보이는 구현 의존성**<br>
**compileOnly : 컴파일에만 사용되는 의존성 정의**<br>
**runtimeOnly : 런타임에만 사용되는 의존성 정의**<br>
**test + Implementation, CompileOnly, RuntimeOnly : 해당 의존성을 테스트 시에만 사용하도록 정의**<br>

Spring 관련 의존성은 <span style="color:#FF6666">컴파일과 런타임 모두에 </span>사용된다.<br>
<span style="color:#3399ff">=> Implementation</span><br>
Lombok은 <span style="color:#FF6666">컴파일시에만 </span>사용된다.<br>
<span style="color:#3399ff">=> compileOnly</span><br>
h2database는 <span style="color:#FF6666">런타임시에만 </span> 사용된다.<br>
<span style="color:#3399ff">=> runtimeOnly</span><br>
Spring-boot-starter-test는 <span style="color:#FF6666">테스트에서만 </span>사용한다.<br>
<span style="color:#3399ff">=> testImplementation</span>