## Flyway란 ❓
Open-Source DB migration tool<br>
누구나 사용할 수 있는 DB 변경관리 도구
<br><br>
code를 깃허브에서 변경, 관리하는 것처럼 DB를 flyway가 변경, 관리하는 것.

## Flyway의 특징 ❓
### 1. Migrate
    DB의 변경을 의미
Ex) <br>
비어있는 DB에서 flyway를 사용해서 Crew 라는 테이블을 만드는 방법?

V1__init.sql 파일을 만들고,

그 안에 create table crew 라고 작성.

그 다음, flyway가 적용된 스프링부트 어플리케이션을 실행

자동적으로 flyway가 crew 테이블을 만들어준다.

* DB의 변경이력을 저장하는 history 테이블도 생긴다.

V1_init.sql 에서 각각은 뜻이 있다.

- V : Version Migration을 의미
    - 새로 적용하려는 파일은 기존에 적용된 파일의 버전보다 높아야 된다.
- 1 : 파일의 버전(unique)
- __ : separator로 __(언더바)가 2개
- init : 파일 설명
- .sql : suffix

### 2. **Baseline**
    
    비어있지 않은 DB에서 flyway를 적용할 때 사용하는 키워드.
    
### 3. **Info**
    
    DB 변경이력을 저장.
    
### 4. **Repair**
    
    실패한 마이그레이션 파일을 다시 복구할 수 있다.
    
### 5. **Validate**
    
    flyway를 적용할 때 DB에 적용할 수 있는지, 없는지 확인할 수 있다.
    
### 6. **Undo**
    
    최근에 적용되었던 Migration 파일을 적용하지 않은 상태로 돌린다.
    
### 7. **Clean**
    
    DB를 깨끗이 지운다.
<br>

## Flyway 사용법 ❗
```gradle
// build.gradle
dependencies {
	implementation 'org.flywaydb:flyway-mysql' // mysql 8.x 이상
	// implementation 'org.flyway:flyway-core' // 일반적
}
```

```yaml
spring:
	flyway:
		enabled: true #flyway를 실행
		url: jdbc:mysql://localhost:3306/%{SCHEMA_NAME} #DB주소
		user: ${DB_USER} #DB user 아이디
		password: ${DB_USER_PASSWORD} #DB user 비밀번호
		baseline-on-migrate: true #baseline 적용
		location: ${NEW_LOCATION} #migration 파일 위치 지정 가능 / 기본위치 : classpath:db/migration
		
```
<br>

## Flyway 사용 이유 ✍🏻
- 실수 방지
    - 프로젝트에서는 local, 개발, 배포, 환경의 DB가 다를 수 있음.
    - Flyway는 런타임 시 자동으로 실행되기 때문에 실수의 여지를 줄여줌
- 환경별 DB 관리
    - 쉽게 DB별 환경을 다르게 가져갈 수 있음
    - local과 개발환경에서는 seed를 넣을 수 있고, 운영 환경에서는 seed를 넣지 않을 수 있음.