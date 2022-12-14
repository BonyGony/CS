# 1. 데이터베이스란?

## 데이터베이스

- 여러 사람이 공유할 목적으로 체계화해 통합, 관리하는 데이터의 집합
- 즉, 자료 파일들을 조직적으로 통합하여 항목의 중복을 없애고 자료를 구조화하여 기억시켜 놓은 자료의 집합체

## 특징

- 실시간 접근성
- 생성, 수정, 삭제를 통한 최신 데이터 유지
- 사용자들 간의 동시 공유
- 데이터 논리적 독립성

## 장점

- 데이터 중복 최소화
- 데이터 공유
- 일관성, 무결성, 보안성 유지
- 데이터의 논리적, 물리적 독립성

## 단점

- 전문가 필요
- 많은 비용 부담
- 데이터 백업과 복구가 어려움
- 시스템의 복잡성

## 모델

- 계층형
  - 데이터 간의 관계가 트리 형태의 구조. 부모-자식 관계. 1:N
  - 구조가 간단하고 구현, 수정, 검색이 쉽지만 N:N 처리가 불가능. 구조적 변경이 어려움
  - IMS
- 네트워크형
  - 계층형 데이터베이스의 단점을 보완. 망 형태로 N:N 구성 가능
  - 유연성과 접근성이 좋지만 구조가 복잡해 유지 보수가 어려움
  - IDMS
- 관계형
  - 키와 값으로 이루어진 데이터들을 행과 열로 구성된 테이블 구조로 단순화시킨 모델
  - SQL을 사용하여 데이터 관리
  - 모델링이 간단하지만 비정형 데이터들을 다루거나 실시간 분석에는 적합하지 않음
  - MySQL, Oracle
- 객체지향형
  - 객체지향 프로그래밍 개념에 기반하여 만든 모델
  - 비정형 데이터들을 데이터베이스화 하기 위해 만들어진 모델
  - 검색이나 대규모 트랜잭션 처리에서 성능이 떨어지는 단점이 있어 몇몇 특수 전문분야에서만 사용
  - O2, ONTOS
- 객체 관계형
  - 관계형 데이터베이스에 객체 지향 개념을 도입하여 만든 데이터베이스 모델
  - 객체지향 개념을 지원하는 표준 SQL을 사용할 수 있고, 데이터 타입도 다양하게 추가되었음
  - UniSQL, Object Store
- NoSQL
  - 데이터 간의 관계를 정의하지 않는 데이터베이스 모델
  - RDBMS의 복잡도와 용량의 한계를 극복하기 위한 목적으로 만들어짐
  - 비정형 데이터 처리에 유리하지만 스키마 변경에 추가적인 작업이 필요
  - MongoDB, DynamoDB, redis

## 데이터베이스 관리 시스템(DataBase Management System, DBMS)란?

- 다수의 사용자들이 데이터베이스 내의 데이터를 접근할 수 있도록 해주는 소프트웨어 도구 집합
- 데이터베이스 생성, 조회, 수정, 삭제와 같은 환경과 각종 응용프로그램이 데이터베이스에 접근할 수 있는 인터페이스를 제공하며 복구, 권한 관리와 같은 보안성 기능도 제공

## DBMS 언어

- SQL은 데이터베이스에서 데이터를 정의, 조작, 제어하기 위해 사용하는 언어
- DDL
  - 데이터베이스나 테이블 등을 생성, 삭제하거나 그 구조를 변경하기 위한 명령어
    - CREATE, ALTER, DROP, TRUNCATE
- DML
  - 데이터베이스에 저장된 데이터를 처리하거나 조회, 검색하기 위한 명령어
    - INSERT, UPDATE, DELETE, SELECT 등
- DCL
  - 데이터베이스에 저장된 데이터를 관리하기 위하여 데이터의 보안성 및 무결성 등을 제어하기 위한 명령어
    - GRANT, REVOKE 등

# 2. 데이터베이스 기본 용어

## Index(인덱스)

- 데이터의 레코드에 빠르게 접근하기 위해 <키 값, 주소> 쌍으로 구성된 데이터 구조
- 데이터가 저장된 물리적 구조와 밀접한 관계를 가지고 있으며 인덱스를 통해 테이블의 레코드에 대해 빠르게 액세스를 할 수 있음

| 파일 시스템 | 데이터베이스 모델링 | 관계형 데이터베이스 |
| :---------: | :-----------------: | :-----------------: |
|    파일     |       엔티티        |       테이블        |
|   레코드    |        튜플         |         행          |
|     키      |       식별자        |       기본키        |
|    필드     |        속성         |         열          |

- 테이블
  - 행과 열로 이루어진 데이터 집합
- 행
  - 관계된 데이터의 묶음. 튜플 또는 레코드라고도 함
- 열
  - 가장 작은 단위의 데이터를 의미. 필드 또는 속성 이라고 함
- 키
  - 테이블에서 행의 식별자로 이용되는 식별자
- 엔티티
  - 현실 세계의 존재하는 객체를 데이터베이스 상에 표현하기 위해 사용한느 추상적인 개념

## 유일성과 최소성

- 유일성
  - 하나의 키로 어떤한 행을 바로 찾아낼 수 있는 성질
  - 주민번호
- 최소성
  - 레코드를 식별하는 데 꼭 필요한 속성들로만 구성되어 있는 성질
  - 주민번호 + 학번 은 최소성을 만족하지 않음. 주민번호로 충분함

## Key의 종류

- 슈퍼 키
  - 테이블의 행을 고유하게 식별할 수 있는 속성 또는 속성의 집합
- 복합 키
  - 2개 이상의 속성(Attribute)을 사용한 키
- 후보 키
  - 유일성과 최소성을 만족하는 키 (각 튜플을 유일하게 식별할 수 있는 속성의 집합)
- 기본 키
  - 후보 키에서 선택된 키 (null 값 혹은 중복 값으로 가질 수 없음)
- 대체 키
  - 후보 키에서 선택되지 않은 키
- 외래 키
  - 서로 다른 테이블 간의 관계를 맺어주는 키 (다른 테이블의 기본키를 참조)

## 차수

- 테이블 내의 속성 수

## 도메인

- Relation에서 각각의 속성에 채워질 수 있는 데이터의 타입과 길이를 의미

## 스키마

- 데이터베이스를 구성하는 데이터 객체, 속성, 레코드 간의 관계 등 데이터베이스의 골격 구조를 나타내는 일종의 도면.
- 스키마는 데이터베이스의 엔티티와 그 엔티티들 간의 관계를 정의하고 어떠한 타입의 데이터가 어느 위치에 적재되어야 하는지, 또 다른 테이블이나 엔티티와 어떠한 관계를 맺는지 정의.
- 스키마의 3계층
  - 외부 스키마
    - 사용자 입장에서 정의한 데이터베이스의 논리 구조
    - 하나의 데이터베이스에는 여러개의 외부 스키마가 있을 수 있음
  - 개념 스키마
    - 데이터베이스의 전체적인 논리구조
    - 사용자가 필요로 하는 데이터를 통합한 조직 전체의 데이터베이스로 하나만 존재하며
    - 객체 간의 관계와 제약조건, 데이터베이스의 접근 권한, 보안 및 무결성 규칙에 관한 명세를 뜻함
  - 내부 스키마
    - 물리적 저장장치 입장에서 본 데이터베이스 구조
    - 데이터베이스에 저장될 레코드의 물리적인 구조, 저장 데이터 항목의 표현 방법, 내부 레코드의 물리적 순서 등을 나타냄

## 트랜잭션

- 데이터베이스 내에서 한꺼번에 모두 수행되어야 할 연산들의 집합
- 하나의 작업 처리를 위한 논리적 작업 단위

## 데이터베이스 언어 종류

- DDL
  - 데이터 정의어
  - 데이터베이스 구조를 정의하는 언어. 데이터를 생성, 수정, 삭제하는 등 전체 골격을 결정하는 역할
- DML
  - 데이터 조작어
  - 데이터베이스 내의 자료를 검색, 삽입, 갱신, 삭제하기 위해 사용되는 언어
- DCL
  - 데이터 제어어
  - 데이터베이스에 저장된 데이터 관리를 위해 데이터의 보안성, 무결성 유지 등을 제어하는 언어

## 무결성

- 정보에 결점이 없도록 유지한느 성질
- 데이터베이스 내에 저장되는 데이터 값들이 항상 일관성을 갖고 데이터의 유효성, 정확성, 안정성을 유지할 수 있도록 하는 제약조건을 두는 데이터베이스의 특성

## 원자값

- 더 이상 분해되지 않는 최소 구성의 단위

## 이상현상

- 테이블을 설계할 때 잘못 설계하여 데이터를 삽입, 삭제, 수정할 때 논리적으로 생기는 오류

- 테이블 내에서 데이터 중복성에 의해 발생되는 데이터 불일치 현상
  - 갱신 이상
    - 중복 데이터 중 일부만 수정되어 데이터 불일치가 일어나는 현상
  - 삽입 이상
    - 중복된 데이터 중 일부만 수정되어 데이터의 모순이 일어난 현상
  - 삭제 이상
    - 특정 정보 삭제 시 다른 정보까지 삭제되어버리는 현상

## 정규화

- 논리적 설계단계에서 발생할 수 있는 종속으로 인한 이상 현상의 문제점을 해결하기 위해, 속성들 간의 종속 관계를 분석하여 여러 개의 릴레이션으로 분해하는 과정

# 3.데이터 무결성

- 데이터 무결성은 데이터의 정확성, 일관성, 유효성이 유지되는 것을 의미합니다. 여기서 정확성이란 중복이나 누락이 없는 상태를 뜻하고, 일관성은 원인과 결과의 의미가 연속적으로 보장되어 변하지 않는 상태를 뜻합니다.
- 만약 데이터베이스에서 데이터 무결성 설계를 하지 않는다면 테이블에 중복된 데이터 존재, 부모와 자식 데이터 간의 논리적 관계 깨짐, 잦은 에러와 재개발 비용 발생 등과 같은 문제가 발생할 것입니다.
- 그렇기 때문에 DBMS에서 데이터의 무결성이 유지되는 것은 중요한 사항이며, 주로 데이터에 적용되는 연산에 제한을 두어 데이터의 무결성을 유지합니다.

## 데이터 무결성 제약조건의 종류와 개념

### 개체 무결성

- 기본 키 제약이라고도 하며, 테이블은 기본키를 지정하고 그에 따른 무결성 원칙을 지켜야 하는 조건
- 기본 키(Primary Key)에는 Null 값이 올 수 없음
- 기본 키는 테이블 내에 오직 하나의 값만 존재해야 함

### 참조 무결성

- 외래 키 제약이라고도 하며, 테이블 간의 참조 관계를 선언하는 제약조건
- 외래 키(Foreign Key)의 값은 Null이거나 참조 릴레이션의 기본키 값과 동일해야 함
- 외래 키 속성은 참조할 수 없는 값을 지닐 수 없음

### 도메인 무결성

- 테이블에 존재하는 필드의 무결성을 보장하기 위한 것으로 필드의 타입, Null 값 허용 등에 대한 사항을 정의하고 올바른 데이터가 입력되었는지 확인하는 조건

### Null무결성

- 테이블의 특정 속성 값이 Null이 될 수 없게 하는 조건

### 고유 무결성

- 테이블의 특정 속성에 대해 각 레코드들이 갖는 값들이 서로 달라야 하는 조건

### 키 무결성

- 하나의 테이블에는 적어도 하나의 키가 존재해야 하는 조건

### 관계 무결성

- 테이블의 어느 한 레코드의 삽입 가능 여부 또는 한 테이블과 다른 테이블의 레코드들 사이의 관계에 대한 적절성 여부를 지정한 조건

## 무결성 제약조건의 장단점

- 장점
  - 스키마를 정의할 때 일관성 조건을 오직 한 번만 명시하고, 데이터베이스가 갱신될 때 DBMS가 자동적으로 일관성 조건을 검사하므로 응용 프로그램들은 일관성 조건을 검사할 필요가 없음
- 단점
  - 프로그래밍 작업이 훨씬 복잡해지고, 무결성 제약조건을 반복해서 구현해야 하고, 무결성 제약조건들 간에 서로 충돌이 발생할 수 있음

# 4. 데이터베이스 제약조건 PK, FK, UK

## 데이터 베이스 제약조건이란?

- 테이블 단위에서 데이터의 무결성을 보장하는 규칙
- 테이블 수정 작업하는 경우 잘못된 트랜잭션 수행을 방지하는 역할
- 테이블 간 제약조건이 있어서 종속성이 있는 경우 테이블 삭제 방지

## PK

- 테이블 생성 시 고유의 단 한 개의 PK설정
- 중복이나 NULL 불가
- 고유 인덱스 자동 생성
- PK 지정 가능한 칼럼이 여러 개 있을 경우, 많이 사용되는 간단한 칼럼을 선택

## FK

- 외부 식별 자키로 테이블 간의 관계를 의미합니다.
- 두 테이블 간의 종속이 필요한 관계이면 그 접점이 되는 칼럼을 FK로 지정하여 서로 참조할 수 있도록 관계를 맺어 줍니다.
- 테이블 간의 잘못된 매핑을 방지하는 역할도 합니다.

## UK

- 고유키입니다.
- 중복된 값을 허용하지만 여러 개 NULL값을 허용합니다.
- 고유 인데스를 자동 생성합니다.

# 5. 인덱스

- 인덱스(Index)란 데이터베이스 테이블에 대한 검색 동작 속도를 높여주는 자료구조입니다.
- 장점
  - 키 값을 통해 테이블에서 검색과 정렬 속도를 향상시킴
- 단점
  - 인덱스를 생성하는 데 시간이 많이 소요됨
  - 인덱스를 관리하기 위해 데이터베이스에 약 10% 정도의 저장공간이 필요
  - 인덱스가 걸려있는 컬럼에서 INSERT, UPDATE, DELETE가 빈번하다면 인덱스의 크기가 비대해져 성능이 떨어질 수 있습니다
- 자료구조
  - B-Tree
    - 가장 위에 Root Block, 중간에 Branch Block, 그리고 맨 아래 Leaf Block으로 이루어져 있습니다.
    - 브랜치 블록은 분기를 위한 목적으로 활용되며 다음 단계를 가리키는 포인터를 가지고 있습니다.
    - 해당 데이터를 가지고 있는 행 위치를 가리키는 레코드 식별자(RID)로 구성되어 있습니다.
    - 시간 복잡도는 O(logn)
  - 해시 테이블
    - 해시 테이블은 해시함수를 사용하여 키를 해시값으로 매핑하고, 이 해시값을 인덱스로 삼아 데이터를 Key와 함께 저장하는 자료구조입니다. (Key, Value)로 데이터들을 저장하며 시간 복잡도가 O(1)이기 때문에 매우 빠른 검색 능력을 보여줍니다.
    - 하지만 Key값이 한 글자만 달라져도 해시값이 완전 다르게 매핑되므로 특정 단어로 시작하는 값, 일부분 검색, 부등호(<,>)와 같은 내용, 전방 일치 등등의 작업을 하고자 할 때는 해시 테이블이 적합하지 않습니다. 해시 테이블은 동등 연산(==)에 특화되어 있으며 주로 메모리 기반의 데이터베이스에 많이 사용됩니다.

# 6. 정규화

- 데이터의 중복을 최소화하고 데이터의 무결성을 향상하며 유연하게 데이터들을 구조화하는 프로세스

## 목적

- 불필요한 중복 데이터를 제거함
- 각종 이상 현상(Anomaly)을 방지
- 데이터베이스 구조 확장 시 재디자인 최소화

## 반정규화

- 시스템의 성능 향상, 개발 및 운영의 편의성 등을 위해 정규화된 데이터 모델을 통합, 중복, 분리하는 과정을 뜻합니다.

## 함수 종속성

- 테이블의 한 필드값(X)이 다른 필드값(Y)을 결정하는 관계를 함수 종속
- 완전함수 종속
  - 종속자가 기본키에만 종속되는 경우
- 부분함수 종속
  - 기본키가 복합키일 경우 기본키를 구성하는 속성 중 일부에게 종속된 경우
- 이행함수 종속
  - 릴레이션에서 X, Y, Z라는 3 개의 속성이 있을 때 X→Y, Y→Z 이란 종속 관계가 있을 경우

모든 속성이 포함된 기본키의 부분집합에 종속된 경우를 완전함수 종속이라고 한다.

## 정규화 과정

- 제 1 정규화
  - 테이블의 칼럼이 원자 값(하나의 값)을 갖도록 테이블을 분해
  - 이상현상
    - 삽입 이상
    - 삭제 이상
    - 갱신 이상
    - 기본키(primary key)가 아닌 속성들이 기본키에 완전 함수 종속되지 못하고 부분 함수 종속되어 있기 때문이다.
- 제 2 정규화
  - 제 1 정규화에 속하면서, 기본키가 아닌 모든 속성이 기본키에 완전 함수 종속된 형태
  - 이상현상
    - 삽입 이상
    - 삭제 이상
    - 갱신 이상
    - 제2 정규형에서 이상현상이 여전히 발생하는 이유는 '이행적 함수 종속성'
- 제 3 정규화
  - 제 2 정규화에 속하면서, 기본키를 제외한 모든 속성이 기본키에 이행적 함수 종속이 되지 않는 형태
  - 이행적 함수 종속이란 A, B, C에 대해 A -> B이고 B -> C 이면 A -> C 가 성립하는 경우
- BCNF
  - 제3 정규형을 조금 더 강화시킨 개념이다. 강한 제3 정규형이라고도 한다.
  - 모든 결정자는 항상 후보키가 되도록 릴레이션을 분해

# 7. 트랜잭션

- 데이터베이스의 상태를 변화시키기 위해 수행하는 작업 단위

## 트랜잭션의 특징

- 원자성
  - 트랜잭션이 DB에 모두 반영되거나 혹은 모두 반영되지 않아야 한다.
- 일관성
  - 트랜잭션의 작업 처리 결과는 항상 일관성이 있어야 한다.
- 독립성
  - 트랜잭션 수행 시 다른 트랜잭션 연산에 끼어들지 못하도록 보장.
- 지속성
  - 성공적으로 완료된 트랜잭션의 결과는 영구적으로 반양되어야 함

## Commit & Rollback

- Commit
  - 하나의 트랜잭션이 성공적으로 끝나서 데이터베이스가 일관성 있는 상태에 있음을 의미
- Rollback
  - 하나의 트랜잭션 처리가 비정상적으로 종료되어 트랜잭션의 원자성이 깨진 상태를 의미. 트랜잭션의 원자성을 지키기 위해 해당 트랜잭션이 행한 모든 연산을 재시작하거나 취소(Undo)함
