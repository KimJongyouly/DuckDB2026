# 강력한 분석 DB, DuckDB — 목차

## [들어가며](pages/00-ch.md)

---

## 1부 — 시작하기

### [제1장: 설치와 환경 구성](pages/01-ch.md)

#### [1.1 DuckDB 설치](pages/01-1.md)
- 플랫폼별 설치 방법 (macOS, Linux, Windows)
- 패키지 매니저를 이용한 설치
- 버전 확인 및 업그레이드

#### [1.2 CLI로 첫 쿼리 실행하기](pages/01-2.md)
- DuckDB CLI 실행 및 기본 명령
- 간단한 SELECT 쿼리 실행
- `.help`, `.exit` 등 메타 커맨드

#### [1.3 DuckDB UI 소개](pages/01-3.md)
- 내장 웹 UI 실행 방법
- 쿼리 편집기 및 결과 시각화
- UI vs CLI 사용 시나리오

---

### [제2장: DuckDB에 연결하기](pages/02-ch.md)

#### [2.1 커넥션 개념 이해](pages/02-1.md)
- DuckDB의 단일 프로세스 아키텍처
- 커넥션 생성과 닫기
- 커넥션 vs 세션 개념

#### [2.2 영구 모드 (Persistent Mode)](pages/02-2.md)
- 파일 기반 데이터베이스 생성
- `.duckdb` 파일 구조
- 재연결 및 데이터 유지

#### [2.3 인메모리 모드 (In-Memory Mode)](pages/02-3.md)
- `:memory:` 연결 방법
- 인메모리 모드의 장단점
- 임시 분석 작업에서의 활용

#### [2.4 디스크 스필링과 대용량 처리](pages/02-4.md)
- 메모리 초과 시 디스크 스필링 동작 원리
- `temp_directory` 설정
- 대용량 쿼리 실행 시 주의사항

#### [2.5 동시성 고려사항](pages/02-5.md)
- 단일 쓰기 / 다중 읽기 모델
- 멀티스레드 환경에서의 커넥션 공유
- WAL(Write-Ahead Log) 없는 설계의 의미

---

## 2부 — SQL 핵심

### [제3장: SQL 기초 및 DuckDB 방언](pages/03-ch.md)

#### [3.1 DuckDB SQL 개요](pages/03-1.md)
- PostgreSQL 호환 SQL 방언
- DuckDB만의 확장 문법 개요
- 표준 SQL과의 차이점

#### [3.2 SELECT 문과 FROM / JOIN](pages/03-2.md)
- 기본 SELECT 구조
- INNER / LEFT / RIGHT / FULL OUTER JOIN
- LATERAL JOIN, CROSS JOIN

#### [3.3 WHERE, GROUP BY, HAVING, ORDER BY, LIMIT](pages/03-3.md)
- 필터링과 집계의 실행 순서
- HAVING으로 집계 결과 필터링
- LIMIT / OFFSET 페이징

#### [3.4 서브쿼리와 CTE](pages/03-4.md)
- 스칼라 서브쿼리, 인라인 뷰
- WITH 절(CTE) 작성법
- 재귀 CTE (Recursive CTE)

#### [3.5 WINDOW 함수와 QUALIFY](pages/03-5.md)
- OVER 절 구조 (PARTITION BY / ORDER BY / FRAME)
- ROW_NUMBER, RANK, DENSE_RANK, NTILE
- QUALIFY로 윈도우 결과 직접 필터링

#### [3.6 SAMPLE, UNNEST, VALUES](pages/03-6.md)
- TABLESAMPLE / USING SAMPLE로 랜덤 샘플링
- UNNEST로 리스트·배열 펼치기
- VALUES 절로 인라인 데이터 생성

#### [3.7 집합 연산](pages/03-7.md)
- UNION / UNION ALL / INTERSECT / EXCEPT
- 컬럼 수·타입 일치 규칙
- 집합 연산과 정렬의 관계

---

### [제4장: 데이터 타입](pages/04-ch.md)

#### [4.1 숫자, 텍스트, 불리언, 날짜/시간](pages/04-1.md)
- INTEGER, BIGINT, DOUBLE, DECIMAL
- VARCHAR, TEXT, BLOB
- DATE, TIME, TIMESTAMP, INTERVAL

#### [4.2 LIST, STRUCT, MAP, UNION](pages/04-2.md)
- 중첩 타입(Nested Type) 개요
- LIST: 동적 배열 생성과 인덱싱
- STRUCT / MAP: 키-값 구조
- UNION 타입으로 복합 스키마 표현

#### [4.3 ENUM, BLOB, ARRAY](pages/04-3.md)
- ENUM 타입 정의와 활용
- 고정 크기 ARRAY vs 가변 LIST
- BLOB: 바이너리 데이터 저장

#### [4.4 타입 캐스팅과 변환](pages/04-4.md)
- CAST / TRY_CAST / :: 연산자
- 암묵적 형변환 규칙
- 날짜·문자열 변환 패턴

---

### [제5장: 함수 완전 정복](pages/05-ch.md)

#### [5.1 집계 함수](pages/05-1.md)
- COUNT, SUM, AVG, MIN, MAX
- APPROX_COUNT_DISTINCT, MEDIAN
- FIRST / LAST / MODE / KURTOSIS

#### [5.2 문자열 함수](pages/05-2.md)
- CONCAT, LENGTH, SUBSTRING, TRIM
- REGEXP_REPLACE, REGEXP_EXTRACT
- FORMAT, PRINTF 스타일 포매팅

#### [5.3 날짜/시간 함수](pages/05-3.md)
- DATE_TRUNC, DATE_PART, EXTRACT
- DATEADD, DATEDIFF
- 타임존 처리 (AT TIME ZONE)

#### [5.4 JSON 함수](pages/05-4.md)
- json_extract, json_extract_string
- json_object, json_array, json_merge_patch
- JSON 경로(JSONPath) 표현식

#### [5.5 수학·통계 함수](pages/05-5.md)
- ROUND, FLOOR, CEIL, ABS, MOD
- STDDEV, VARIANCE, CORR, COVAR
- QUANTILE, RESERVOIR_QUANTILE

#### [5.6 리스트·맵·구조체 함수](pages/05-6.md)
- list_append, list_concat, list_filter, list_transform
- map_keys, map_values, map_extract
- struct_extract, struct_pack

#### [5.7 윈도우 함수 심화](pages/05-7.md)
- LAG / LEAD로 이전·다음 행 참조
- FIRST_VALUE / LAST_VALUE / NTH_VALUE
- ROWS vs RANGE vs GROUPS 프레임

---

### [제6장: DDL과 DML](pages/06-ch.md)

#### [6.1 테이블 생성·변경·삭제](pages/06-1.md)
- CREATE TABLE 기본 및 옵션
- ALTER TABLE: 컬럼 추가·변경·삭제
- DROP TABLE / TRUNCATE

#### [6.2 INSERT, UPDATE, DELETE, UPSERT](pages/06-2.md)
- INSERT INTO ... VALUES / SELECT
- UPDATE SET 문법
- DELETE FROM 조건부 삭제
- INSERT OR REPLACE (UPSERT)

#### [6.3 인덱스와 제약조건](pages/06-3.md)
- 최소한의 인덱스 지원 구조
- PRIMARY KEY, UNIQUE, NOT NULL
- CHECK 제약조건

#### [6.4 뷰(VIEW)와 시퀀스](pages/06-4.md)
- CREATE VIEW / DROP VIEW
- 뷰를 이용한 쿼리 추상화
- SEQUENCE 생성 및 NEXTVAL

#### [6.5 트랜잭션과 VACUUM / ANALYZE](pages/06-5.md)
- BEGIN / COMMIT / ROLLBACK
- 자동 커밋 모드
- VACUUM으로 저장 공간 회수, ANALYZE로 통계 갱신

---

## 3부 — 데이터 가져오기·내보내기

### [제7장: CSV 파일](pages/07-ch.md)

#### [7.1 CSV 읽기](pages/07-1.md)
- `read_csv()` 함수 기본 사용법
- 자동 스키마 감지 (Auto-detect)
- 구분자·인코딩·헤더 옵션

#### [7.2 손상된 CSV 처리](pages/07-2.md)
- `ignore_errors` 옵션으로 오류 행 건너뛰기
- `null_padding`, `quote` 옵션
- 문제 행 디버깅 방법

#### [7.3 CSV 쓰기와 옵션](pages/07-3.md)
- `COPY TO` 문으로 CSV 내보내기
- 구분자·헤더 포함 여부 설정
- 대용량 파일 분할 출력

---

### [제8장: JSON 파일](pages/08-ch.md)

#### [8.1 JSON 읽기·쓰기](pages/08-1.md)
- `read_json()` / `read_json_auto()` 함수
- `COPY TO ... FORMAT JSON`
- NDJSON (Newline-Delimited JSON) 처리

#### [8.2 JSON 타입과 함수](pages/08-2.md)
- JSON 네이티브 타입 저장
- `->>`, `->` 연산자
- JSON 집계 함수

#### [8.3 중첩 JSON 펼치기](pages/08-3.md)
- UNNEST로 배열 행 변환
- json_transform으로 스키마 명시
- 복잡한 중첩 구조 처리 패턴

---

### [제9장: Parquet 파일](pages/09-ch.md)

#### [9.1 Parquet 읽기·쓰기](pages/09-1.md)
- `read_parquet()` 함수
- `COPY TO ... FORMAT PARQUET`
- 컬럼형 저장의 성능 이점

#### [9.2 메타데이터 활용](pages/09-2.md)
- `parquet_metadata()`, `parquet_schema()` 함수
- Row Group 통계로 푸시다운 최적화
- 파일 구조 시각화

#### [9.3 Parquet 암호화](pages/09-3.md)
- Parquet 암호화 표준 (AES-GCM)
- DuckDB에서 암호화 설정 방법
- 키 관리 주의사항

---

### [제10장: 다중 파일과 파티셔닝](pages/10-ch.md)

#### [10.1 와일드카드로 여러 파일 읽기](pages/10-1.md)
- `*.parquet`, `**/*.csv` 글로브 패턴
- 파일 목록을 쿼리로 확인하기
- 파일 이름을 컬럼으로 포함하기 (`filename` 옵션)

#### [10.2 스키마 통합](pages/10-2.md)
- `union_by_name`으로 컬럼명 기반 병합
- 타입 불일치 처리 전략
- 누락 컬럼 NULL 채우기

#### [10.3 Hive 파티셔닝](pages/10-3.md)
- `key=value` 디렉터리 구조 인식
- `hive_partitioning=true` 옵션
- 파티션 프루닝으로 스캔 최소화

#### [10.4 파티션 쓰기](pages/10-4.md)
- `PARTITION BY` 절로 파일 분할 저장
- 출력 파일명 패턴 설정
- 기존 파티션 덮어쓰기·추가 전략

---

### [제11장: 레이크하우스 포맷](pages/11-ch.md)

#### [11.1 Apache Iceberg](pages/11-1.md)
- Iceberg 테이블 포맷 개요
- DuckDB에서 Iceberg 카탈로그 연결
- 스냅샷·타임트래블 쿼리

#### [11.2 Delta Lake](pages/11-2.md)
- Delta 트랜잭션 로그 구조
- `delta_scan()` 함수 사용법
- DML 변경 이력 조회

#### [11.3 INSERT 문과 Appender API](pages/11-3.md)
- 배치 INSERT 성능 고려
- C++ / Python Appender API로 고속 적재
- 레이크하우스 테이블에 데이터 추가

---

## 4부 — 클라이언트 API

### [제12장: Python과 DuckDB](pages/12-ch.md)

#### [12.1 설치 및 기본 연결](pages/12-1.md)
- `pip install duckdb`
- `duckdb.connect()` 인메모리 / 파일 모드
- `execute()`, `fetchall()`, `fetchdf()`

#### [12.2 Pandas / Polars / Arrow와 연동](pages/12-2.md)
- DataFrame을 직접 쿼리하기 (Zero-copy)
- `duckdb.from_df()`, `duckdb.from_arrow()`
- 결과를 DataFrame / Arrow Table로 변환

#### [12.3 관계형 API (Relational API)](pages/12-3.md)
- `duckdb.table()`, `.filter()`, `.project()`, `.aggregate()`
- 지연 실행(Lazy Evaluation) 개념
- SQL 없이 파이프라인 구성

#### [12.4 Jupyter Notebook에서 활용](pages/12-4.md)
- `%load_ext duckdb_magic` 매직 커맨드
- 인터랙티브 쿼리 실행
- 결과 시각화 (Matplotlib / Altair 연동)

---

### [제13장: CLI 심화](pages/13-ch.md)

#### [13.1 CLI 옵션과 설정](pages/13-1.md)
- 시작 옵션 (`-c`, `-f`, `-s`, `-json` 등)
- `.duckdbrc` 초기화 파일
- 출력 형식 변경 (`.mode`, `.separator`)

#### [13.2 스크립트 자동화](pages/13-2.md)
- 셸 스크립트에서 DuckDB 호출
- `-c "SQL"` 원라이너 실행
- 결과를 파이프로 다른 도구에 전달

---

### [제14장: 기타 클라이언트](pages/14-ch.md)

#### [14.1 Java (JDBC)](pages/14-1.md)
- `duckdb-jdbc` 드라이버 추가
- JDBC URL 및 Connection 생성
- PreparedStatement와 ResultSet 처리

#### [14.2 Node.js](pages/14-2.md)
- `@duckdb/node-api` 패키지
- 비동기(async/await) 쿼리 실행
- Buffer / Arrow IPC 결과 처리

#### [14.3 Go, Rust, R](pages/14-3.md)
- Go: `go-duckdb` CGO 바인딩
- Rust: `duckdb-rs` 크레이트
- R: `duckdb` 패키지와 DBI 인터페이스

#### [14.4 ODBC / ADBC](pages/14-4.md)
- ODBC 드라이버 설치 및 DSN 설정
- ADBC(Arrow Database Connectivity) 개요
- BI 도구(Tableau, Power BI) 연결

#### [14.5 WebAssembly](pages/14-5.md)
- `@duckdb/duckdb-wasm` 패키지
- 브라우저에서 로컬 쿼리 실행
- 파일 시스템 API 연동

---

## 5부 — 확장과 생태계

### [제15장: 핵심 확장 활용](pages/15-ch.md)

#### [15.1 Extension 설치](pages/15-1.md)
- `INSTALL` / `LOAD` 명령
- 자동 로딩 설정
- 커뮤니티 Extension 목록

#### [15.2 httpfs: HTTP/S3 파일 직접 쿼리](pages/15-2.md)
- HTTP URL에서 Parquet/CSV 직접 읽기
- S3 버킷 연결 및 인증 설정
- 글로브 패턴으로 S3 다중 파일 스캔

#### [15.3 AWS / Azure 연동](pages/15-3.md)
- `aws` Extension으로 자격증명 자동 로드
- Azure Blob Storage 연결
- GCS(Google Cloud Storage) 연동

#### [15.4 Spatial: 공간 데이터 분석](pages/15-4.md)
- `spatial` Extension 설치
- GEOMETRY 타입과 공간 함수
- GeoJSON / Shapefile 읽기

#### [15.5 Full-Text Search](pages/15-5.md)
- `fts` Extension으로 전문 검색 인덱스 생성
- `fts_main_*` 테이블 구조
- MATCH / SCORE 쿼리

#### [15.6 Excel 읽기](pages/15-6.md)
- `spatial` Extension의 `st_read()` 또는 `excel` Extension
- `.xlsx` 파일 직접 쿼리
- 시트 선택 및 범위 지정

---

### [제16장: 데이터베이스 연동](pages/16-ch.md)

#### [16.1 PostgreSQL 연동](pages/16-1.md)
- `postgres` Extension으로 직접 쿼리
- `ATTACH 'postgres://...'` 방법
- 로컬 PostgreSQL 데이터 분석 워크플로

#### [16.2 MySQL 연동](pages/16-2.md)
- `mysql` Extension 설치
- MySQL 테이블을 DuckDB에서 조회
- 데이터 이관 패턴

#### [16.3 SQLite 연동](pages/16-3.md)
- `sqlite` Extension으로 `.db` 파일 ATTACH
- SQLite 테이블 직접 읽기·쓰기
- 경량 ETL 파이프라인 구성

---

## 6부 — 성능 최적화와 실전 운영

### [제17장: 설정과 튜닝](pages/17-ch.md)

#### [17.1 설정(Configuration) 개요](pages/17-1.md)
- `SET`, `RESET`, `PRAGMA` 명령
- 전역 vs 세션 설정 범위
- 주요 설정 파라미터 일람

#### [17.2 Pragmas 활용](pages/17-2.md)
- `PRAGMA database_list`, `PRAGMA table_info`
- `PRAGMA memory_limit`, `PRAGMA threads`
- 통계·진단용 Pragma

#### [17.3 Secrets Manager](pages/17-3.md)
- `CREATE SECRET` 문으로 자격증명 저장
- 영구(Persistent) vs 임시(Temporary) Secret
- S3 / Azure 자격증명 관리 패턴

---

### [제18장: 성능 최적화](pages/18-ch.md)

#### [18.1 실행 계획(EXPLAIN) 읽기](pages/18-1.md)
- `EXPLAIN` / `EXPLAIN ANALYZE` 출력 구조
- 물리 연산자(PhysicalOperator) 이해
- 병목 구간 식별 방법

#### [18.2 병렬 처리와 메모리 관리](pages/18-2.md)
- 자동 멀티스레드 쿼리 실행
- `threads` / `memory_limit` 설정
- 벡터화 실행 엔진(SIMD) 개요

#### [18.3 대용량 데이터 처리 전략](pages/18-3.md)
- 스트리밍 쿼리 vs 풀 로드
- 디스크 스필링 모니터링
- 파티셔닝·프루닝으로 스캔 최소화

---

### [제19장: 운영 및 보안](pages/19-ch.md)

#### [19.1 Docker로 배포하기](pages/19-1.md)
- DuckDB CLI Docker 이미지 활용
- 볼륨 마운트로 영구 데이터 유지
- DuckDB 기반 서비스 컨테이너 구성

#### [19.2 로깅과 모니터링](pages/19-2.md)
- `enable_progress_bar`, `enable_profiling` 설정
- 쿼리 프로파일링 JSON 출력 분석
- 외부 모니터링 도구 연동

#### [19.3 보안 고려사항](pages/19-3.md)
- 파일 접근 권한과 실행 모드
- `enable_external_access` 제한
- 멀티테넌트 환경에서의 격리 전략

#### [19.4 제한(Limits)과 트러블슈팅](pages/19-4.md)
- 알려진 제약사항 (동시 쓰기, 트랜잭션)
- 오류 메시지별 해결 방법
- GitHub Issues 및 커뮤니티 리소스

---

## 7부 — 실전 프로젝트

### [제20장: 데이터 분석 파이프라인 구축](pages/20-ch.md)

#### [20.1 로컬 데이터 레이크 만들기](pages/20-1.md)
- 로컬 Parquet 파일 기반 레이크 설계
- DuckDB로 수집·변환·적재(ETL) 구성
- 데이터 버전 관리 전략

#### [20.2 S3 + Parquet + DuckDB 분석 환경](pages/20-2.md)
- S3 버킷에서 직접 쿼리하는 서버리스 분석
- Hive 파티셔닝 + 프루닝 최적화
- 비용 최소화 쿼리 설계

#### [20.3 실시간 대시보드 연동](pages/20-3.md)
- Streamlit / Gradio와 DuckDB 통합
- 쿼리 결과 캐싱 전략
- 인터랙티브 필터 UI 구성

---

### [제21장: DuckDB로 ML 전처리](pages/21-ch.md)

#### [21.1 대용량 피처 엔지니어링](pages/21-1.md)
- SQL로 피처 변환·정규화·인코딩
- Window 함수를 이용한 시계열 피처
- 학습용 데이터셋 샘플링 전략

#### [21.2 Python ML 파이프라인과 통합](pages/21-2.md)
- Pandas / Polars DataFrame으로 직접 전달
- scikit-learn / PyTorch 연동 패턴
- 대용량 데이터 배치 처리 루프

---

## [부록](pages/22-ch.md)

### [A. SQL 빠른 참조 (Cheat Sheet)](pages/22-A.md)
- 자주 쓰는 DuckDB SQL 패턴 모음
- 파일 읽기·쓰기 원라이너
- 타입 변환 및 날짜 처리 레퍼런스

### [B. 주요 함수 레퍼런스](pages/22-B.md)
- 집계·문자열·날짜·JSON·List 함수 목록
- 함수 시그니처 및 반환 타입
- 사용 예제

### [C. 확장 목록과 설치 명령](pages/22-C.md)
- 공식 Extension 전체 목록
- 커뮤니티 Extension 소개
- 버전별 호환성 정보