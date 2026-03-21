# 강력한 분석 DB, DuckDB

DuckDB의 기초부터 실전 파이프라인까지 다루는 실전 가이드입니다.
설치와 SQL 기초에서 출발해 다양한 파일 포맷 처리, 멀티 클라이언트 API, 확장 기능, 성능 최적화, 그리고 메달리온 아키텍처 기반의 데이터 파이프라인 구축까지 단계별로 다룹니다.
각 챕터는 독립 실행 가능한 예제 데이터를 포함하며, CLI·Python·Java·Node.js 등 다양한 환경을 지원합니다.

---

## 들어가며

- DuckDB란 무엇인가
- 왜 DuckDB인가: SQLite vs PostgreSQL vs DuckDB
- 이 책의 구성과 독자 대상

---

## 챕터 구성

### 1부 — 시작하기

| 챕터 | 제목 | 핵심 내용 |
|------|------|-----------|
| 1장 | 설치와 환경 구성 | CLI·Python·Java·Node.js 설치, CLI 첫 쿼리, DuckDB UI 소개 |
| 2장 | DuckDB에 연결하기 | 커넥션 개념, 영구 모드, 인메모리 모드, 디스크 스필링, 동시성 |

### 2부 — SQL 핵심

| 챕터 | 제목 | 핵심 내용 |
|------|------|-----------|
| 3장 | SQL 기초 및 DuckDB 방언 | SELECT, JOIN, GROUP BY, CTE, 윈도우 함수, SAMPLE, UNNEST |
| 4장 | 데이터 타입 | 숫자·텍스트·날짜, LIST, STRUCT, MAP, UNION, ENUM, ARRAY, 타입 캐스팅 |
| 5장 | 함수 완전 정복 | 집계·문자열·날짜·JSON·수학·통계·리스트·윈도우 함수 |
| 6장 | DDL과 DML | 테이블 생성·변경, INSERT·UPDATE·DELETE·UPSERT, 인덱스, 뷰, 트랜잭션 |

### 3부 — 데이터 가져오기·내보내기

| 챕터 | 제목 | 핵심 내용 |
|------|------|-----------|
| 7장 | CSV 파일 | 자동 타입 감지, 오염 데이터 처리, 다양한 쓰기 옵션 |
| 8장 | JSON 파일 | 읽기·쓰기, JSON 타입·함수, 중첩 구조 언네스팅 |
| 9장 | Parquet 파일 | 읽기·쓰기, 메타데이터, 암호화 |
| 10장 | 다중 파일과 파티셔닝 | 와일드카드, 스키마 합치기, Hive 파티셔닝, 파티션 쓰기 |
| 11장 | 레이크하우스 포맷 | Apache Iceberg, Delta Lake, Appender API |

### 4부 — 클라이언트 API

| 챕터 | 제목 | 핵심 내용 |
|------|------|-----------|
| 12장 | Python과 DuckDB | 설치·연결, Pandas·Polars·PyArrow 연동, Relational API, Jupyter |
| 13장 | CLI 심화 | 옵션, 설정, 스크립트 자동화 |
| 14장 | 기타 클라이언트 | Java(JDBC), Node.js, Go, Rust, R, ODBC, ADBC, WebAssembly |

### 5부 — 확장과 생태계

| 챕터 | 제목 | 핵심 내용 |
|------|------|-----------|
| 15장 | 핵심 확장 활용 | httpfs(HTTP/S3), AWS·Azure, 공간 분석, 전문 검색, Excel |
| 16장 | 데이터베이스 연동 | PostgreSQL, MySQL, SQLite 연결 |

### 6부 — 성능 최적화와 실전 운영

| 챕터 | 제목 | 핵심 내용 |
|------|------|-----------|
| 17장 | 설정과 튜닝 | Pragma, Secrets Manager |
| 18장 | 성능 최적화 | EXPLAIN, 병렬 처리, 메모리 관리, 대용량 전략 |
| 19장 | 운영 및 보안 | Docker 배포, 로깅·모니터링, 보안, 한계, 트러블슈팅 |

### 7부 — 실전 프로젝트

| 챕터 | 제목 | 핵심 내용 |
|------|------|-----------|
| 20장 | 데이터 분석 파이프라인 구축 | 메달리온 아키텍처(Bronze/Silver/Gold), 로컬 데이터 레이크, S3+Parquet, 대시보드 연동 |
| 21장 | DuckDB로 ML 전처리 | 대규모 피처 엔지니어링, Python ML 파이프라인 연동 |

### 부록

| | 제목 |
|-|------|
| 부록 A | SQL 빠른 참조 (Cheat Sheet) |
| 부록 B | 주요 함수 레퍼런스 |
| 부록 C | 확장 목록과 설치 명령 |


## 사전 요구사항

| 항목 | 버전 / 설치 방법 |
|------|-----------------|
| DuckDB CLI | `brew install duckdb` / [공식 릴리스](https://github.com/duckdb/duckdb/releases) |
| Python | 3.9 이상, `pip install duckdb` |
| Java | JDK 11 이상, Maven/Gradle로 JDBC 드라이버 추가 |
| Node.js | 16 이상, `npm install duckdb` |
| (선택) Apache Arrow | Parquet·Arrow 연동 시 필요 |
| (선택) AWS CLI | S3 연동(httpfs Extension) 시 필요 |

> `*.db` 파일(영구 데이터베이스)은 커밋하지 않습니다.
> 각 챕터의 예제는 `assets/` 경로의 샘플 데이터만으로 독립 실행할 수 있습니다.
