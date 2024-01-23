# DB   

<details>
<summary>❓ 데이터베이스의 특징에 대해 설명해주세요.</summary>
<div markdown="1">

1. **실시간 접근성(Real-Time Accessibility)**
비정형적인 질의(조회)에 대하여 실시간 처리에 의한 응답이 가능해야 하며,
2. **지속적인 변화(Continuous Evolution)**
데이터베이스의 상태는 동적입니다. 즉, 새로운 데이터의 삽입(Insert), 삭제(Delete), 갱신(Update)으로 항상 최신의 데이터를 유지해야 합니다.
3. **동시 공용(Concurrent Sharing)**
데이터베이스는 서로 다른 목적을 가진 여러 응용자들을 위한 것이므로 다수의 사용자가 동시에 같은 내용의 데이터를 이용할 수 있어야 합니다.
4. **내용에 의한 참조(Content Reference)**
데이터베이스에 있는 데이터를 참조할 때 데이터 레코드의 주소나 위치에 의해서가 아니라 사용자가 요구하는 데이터 내용으로 찾습니다.

</div>
</details>

<details>
<summary>❓ 데이터베이스 언어(DDL, DML, DCL)에 대해 설명해주세요.</summary>
<div markdown="1">

**DDL (정의어: Data Definition Language)**<br>
테이블
데이터베이스 구조를 정의, 수정, 삭제하는 언어<br>- create, alter, drop

**DML (조작어: Data Manipulation Language)**<br>
테이블 내 컬럼
데이터베이스내의 자료 검색, 삽입, 갱신, 삭제를 위한 언어<br> - insert, select, update, delete

**DCL (제어어: Data Control Language)**<br>
권한
데이터에 대해 무결성 유지, 병행 수행 제어, 보호와 관리를 위한 언어<br>- commit, rollback, grant, revoke


</div>
</details>

<details>
<summary>❓ SELECT 쿼리의 수행 순서를 알려주세요.</summary>
<div markdown="1">

> FROM, ON, JOIN ➡️ WHERE ➡️ GROUP BY ➡️ HAVING ➡️ SELECT ➡️ DISTINCT ➡️ ORDER BY ➡️ LIMIT
> 
1. FROM: 각테이블을 확인한다.
ON: JOIN 조건을 확인한다.
JOIN: JOIN이 실행되어 데이터가 SET으로 모아지게 된다. 서브쿼리도 함께 포함되어 임시 테이블을 만들 수 있게 도와준다.
2. WHERE: 데이터셋을 형성하게 되면 WHERE 조건이 개별 행에 적용된다. WHERE 절의 제약 조건은 FROM 절로 가져온 테이블에 적용될 수 있다.
3. GROUP BY: WHERE 조건 적용 후 나머지 행은 GROUP BY 절에 지정된 열의 공통 값을 기준으로 그룹화된다. 쿼리에 집계  기능이 있는 경우에만 이 기능을 사용해야 한다.
4. HAVING: GROUP BY 절이 쿼리에 있을 경우, HAVING 절의 제약조건이 그룹화된 행에 적용된다.
5. SELECT: SELECT에 표현된 식이 마지막으로 적용된다.
6. DISTINCT: 표현된 행에서 중복된 행은 삭제
7. ORDER BY: 지정된 데이터를 기준으로 오름차순, 내림차순 지정
8. LIMIT: LIMIT에서 벗어나는 행들은 제외되어 출력된다.


</div>
</details>

<details>
<summary>❓ 트리거(Trigger)에 대해 설명해주세요.</summary>
<div markdown="1">

- 트리거는 특정 테이블에 대한 이벤트에 반응해 INSERT, DELETE, UPDATE 같은 DML 문이 수행되었을 때, 데이터베이스에서 자동으로 동작하도록 작성된 프로그램입니다.
- 사용자가 직접 호출하는 것이 아닌, 데이터베이스에서 자동적으로 호출한다는 것이 가장 큰 특징입니다.

</div>
</details>