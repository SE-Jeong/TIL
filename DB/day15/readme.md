## 2021. 11. 19

#### 데이터베이스 표준 질의어 (SQL [Structured Query Language])

- 관계형 데이터베이스 관리 시스템(RDBMS)의 데이터베이스, 데이터를 관리하기 위해 설계된 특수 목적의 프로그래밍 언어
- 질의어(Query Language)는 검색 언어라는의이지만데이터를 검색하는 역할 외에 데이터 입력, 수정, 삭제, 제어, 복구 등 다양한 기능을 제공하는 종합 저인 언어
- ‘ 에스큐엘’ 또는 ‘시퀄’ 로 읽음DBMS 제품 별 특화된 SQL 사용



### SQL문의 기능별 분류

#### 데이터 정의어 (DDL)

- 데이터베이스, 테이블 구조를 생성/수정/삭제하는 데 사용
  - CREATE / ALTER / DROP 문

#### 데이터 조작어 (DML)

- 테이블의 데이터를 검색, 삽입, 수정, 삭제하는데 사용
  - SELECT / INSERT / UPDATE / DELETE 문

#### 데이터 제어어 (DCL)

- 데이터의 사용 권한 등 관리에 사용
  - GRANT : 권한 부여
  - REVOKE : 권한 취소
  - COMMIT : 변경된 내용을 영구적으로 DB를 반영
  - ROLLBACK : 변경된 내용을 취소하고 DB를 이전 상태로 되돌림

#### 데이터 정의어 (DDL)

- 데이터베이스, 테이블 구조를 생성/수정/삭제하는 데 사용
- 스키마, 테이블, 뷰, 인덱스 정의, 변경, 삭제할 때 사용하는 명령문
  - CREATE  : 데이터베이스, 테이블 등
  - ALTER : 기존에 존재하는 데이터베이스 등 객체 변경
  - DROP : 데이터베이스 등 객체 삭제



|          표기형식          |                   설명                    |
| :------------------------: | :---------------------------------------: |
|          NOT NULL          |           빈 값을 허용하지 않음           |
|          DEFAULT           |              기본값으로 설정              |
|        PRIMARY KEY         |               기본키  설정                |
|        FOREIGN KEY         |                외래키 설정                |
|         REFERENCES         | 외래키가 참조할 테이블 (부모 테이블) 설정 |
|           UNIQUE           |  중복값이 없도록 설정 (대체키 설정 의미)  |
|           CHECK            |        특정 내용의 제약 조건 설정         |
| ON DELETE / ON UPDATE 옵션 | 참조되는 테이블의 행 삭제 / 갱신 시 옵션  |

#### PRIMARY KEY 제약조건

- 기본키 제약조건
- 열에 지정
- 빈 값 안 됨 (자동으로 중복 안 됨)

❗️CREATE 하고 나면 반드시 Refresh All 해서 새로 고침하고 생성된 것 확인, 아니면 already exists 오류 발생❗️



### ALTER문 (테이블 수정)

- 테이블에 대한 정의 (구조) 변경
- 새로운 열 추가, 특정 열의 디폴트값 변경, 특정 열 삭제 등 수행

#### ALTER문의 기본 형식

- ALTER TABLE 테이블명
  - ADD : 열 추가
  - RENAME COLUMN : 열 이름 변경
  - MODIGY : 열의 데이터 형식 변경
  - CHANGE : 열 이름과 데이터 형식 동시 변경
  - DROP COLUMN : 열 삭제