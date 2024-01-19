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