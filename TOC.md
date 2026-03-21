# 강력한 분석 DB, DuckDB — 목차

## [들어가며](pages/00_들어가며.md)

## 1부 — 시작하기

## [제1장: 설치와 환경 구성](pages/01_설치와환경구성.md)

### [1.1 DuckDB 설치](pages/01_설치와환경구성.md#11-duckdb-설치)

### [1.2 CLI로 첫 쿼리 실행하기](pages/01_설치와환경구성.md#12-cli로-첫-쿼리-실행하기)

### [1.3 DuckDB UI 소개](pages/01_설치와환경구성.md#13-duckdb-ui-소개)



## [제2장: DuckDB에 연결하기](pages/02_duckdb에_연결하기.md)

### [2.1 커넥션 개념 이해](pages/02_duckdb에_연결하기.md#21-커넥션-개념-이해)

### [2.2 영구 모드 (Persistent Mode)](pages/02_duckdb에_연결하기.md#22-영구-모드-persistent-mode)

### [2.3 인메모리 모드 (In-Memory Mode)](pages/02_duckdb에_연결하기.md#23-인메모리-모드-in-memory-mode)

### [2.4 디스크 스필링과 대용량 처리](pages/02_duckdb에_연결하기.md#24-디스크-스필링과-대용량-처리)

### [2.5 동시성 고려사항](pages/02_duckdb에_연결하기.md#25-동시성-고려사항)



## 2부 — SQL 핵심

## [제3장: SQL 기초 및 DuckDB 방언](pages/03_SQL기초.md)

### [3.1 DuckDB SQL 개요](pages/03_SQL기초.md#31-duckdb-sql-개요)

### [3.2 SELECT 문과 FROM / JOIN](pages/03_SQL기초.md#32-select-문과-from--join)

### [3.3 WHERE, GROUP BY, HAVING, ORDER BY, LIMIT](pages/03_SQL기초.md#33-where-group-by-having-order-by-limit)

### [3.4 서브쿼리와 CTE](pages/03_SQL기초.md#34-서브쿼리와-cte)

### [3.5 WINDOW 함수와 QUALIFY](pages/03_SQL기초.md#35-window-함수와-qualify)

### [3.6 SAMPLE, UNNEST, VALUES](pages/03_SQL기초.md#36-sample-unnest-values)

### [3.7 집합 연산](pages/03_SQL기초.md#37-집합-연산)



## [제4장: 데이터 타입](pages/04_데이터타입.md)

### [4.1 숫자, 텍스트, 불리언, 날짜/시간](pages/04_데이터타입.md#41-숫자-텍스트-불리언-날짜시간)

### [4.2 LIST, STRUCT, MAP, UNION](pages/04_데이터타입.md#42-list-struct-map-union)

### [4.3 ENUM, BLOB, ARRAY](pages/04_데이터타입.md#43-enum-blob-array)

### [4.4 타입 캐스팅과 변환](pages/04_데이터타입.md#44-타입-캐스팅과-변환)



## [제5장: 함수 완전 정복](pages/05_함수완전정복.md)

### [5.1 집계 함수](pages/05_함수완전정복.md#51-집계-함수)

### [5.2 문자열 함수](pages/05_함수완전정복.md#52-문자열-함수)

### [5.3 날짜/시간 함수](pages/05_함수완전정복.md#53-날짜시간-함수)

### [5.4 JSON 함수](pages/05_함수완전정복.md#54-json-함수)

### [5.5 수학·통계 함수](pages/05_함수완전정복.md#55-수학통계-함수)

### [5.6 리스트·맵·구조체 함수](pages/05_함수완전정복.md#56-리스트맵구조체-함수)

### [5.7 윈도우 함수 심화](pages/05_함수완전정복.md#57-윈도우-함수-심화)



## [제6장: DDL과 DML](pages/06_DDL과DML.md)

### [6.1 테이블 생성·변경·삭제](pages/06_DDL과DML.md#61-테이블-생성변경삭제)

### [6.2 INSERT, UPDATE, DELETE, UPSERT](pages/06_DDL과DML.md#62-insert-update-delete-upsert)

### [6.3 인덱스와 제약조건](pages/06_DDL과DML.md#63-인덱스와-제약조건)

### [6.4 뷰(VIEW)와 시퀀스](pages/06_DDL과DML.md#64-뷰view와-시퀀스)

### [6.5 트랜잭션과 VACUUM / ANALYZE](pages/06_DDL과DML.md#65-트랜잭션과-vacuum--analyze)



## 3부 — 데이터 가져오기·내보내기

## [제7장: CSV 파일](pages/07_csv.md)

### [7.1 CSV 읽기](pages/07_csv.md#71-csv-읽기)

### [7.2 손상된 CSV 처리](pages/07_csv.md#72-손상된-csv-처리)

### [7.3 CSV 쓰기와 옵션](pages/07_csv.md#73-csv-쓰기와-옵션)



## [제8장: JSON 파일](pages/08_json.md)

### [8.1 JSON 읽기·쓰기](pages/08_json.md#81-json-읽기쓰기)

### [8.2 JSON 타입과 함수](pages/08_json.md#82-json-타입과-함수)

### [8.3 중첩 JSON 펼치기](pages/08_json.md#83-중첩-json-펼치기)



## [제9장: Parquet 파일](pages/09_parquet.md)

### [9.1 Parquet 읽기·쓰기](pages/09_parquet.md#91-parquet-읽기쓰기)

### [9.2 메타데이터 활용](pages/09_parquet.md#92-메타데이터-활용)

### [9.3 Parquet 암호화](pages/09_parquet.md#93-parquet-암호화)



## [제10장: 다중 파일과 파티셔닝](pages/10_다중파일_파티션.md)

### [10.1 와일드카드로 여러 파일 읽기](pages/10_다중파일_파티션.md#101-와일드카드로-여러-파일-읽기)

### [10.2 스키마 통합](pages/10_다중파일_파티션.md#102-스키마-통합)

### [10.3 Hive 파티셔닝](pages/10_다중파일_파티션.md#103-hive-파티셔닝)

### [10.4 파티션 쓰기](pages/10_다중파일_파티션.md#104-파티션-쓰기)



## [제11장: 레이크하우스 포맷](pages/11_레이크하우스.md)

### [11.1 Apache Iceberg](pages/11_레이크하우스.md#111-apache-iceberg)

### [11.2 Delta Lake](pages/11_레이크하우스.md#112-delta-lake)

### [11.3 INSERT 문과 Appender API](pages/11_레이크하우스.md#113-insert-문과-appender-api)



## 4부 — 클라이언트 API

## [제12장: Python과 DuckDB](pages/12_Python_duckdb.md)

### [12.1 설치 및 기본 연결](pages/12_Python_duckdb.md#121-설치-및-기본-연결)

### [12.2 Pandas / Polars / Arrow와 연동](pages/12_Python_duckdb.md#122-pandas--polars--arrow와-연동)

### [12.3 관계형 API (Relational API)](pages/12_Python_duckdb.md#123-관계형-api-relational-api)

### [12.4 Jupyter Notebook에서 활용](pages/12_Python_duckdb.md#124-jupyter-notebook에서-활용)



## [제13장: CLI 심화](pages/13_CLI심화.md)

### [13.1 CLI 옵션과 설정](pages/13_CLI심화.md#131-cli-옵션과-설정)

### [13.2 스크립트 자동화](pages/13_CLI심화.md#132-스크립트-자동화)



## [제14장: 기타 클라이언트](pages/14_기타_클라이언트.md)

### [14.1 Java (JDBC)](pages/14_기타_클라이언트.md#141-java-jdbc)

### [14.2 Node.js](pages/14_기타_클라이언트.md#142-nodejs)

### [14.3 Go, Rust, R](pages/14_기타_클라이언트.md#143-go-rust-r)

### [14.4 ODBC / ADBC](pages/14_기타_클라이언트.md#144-odbc--adbc)

### [14.5 WebAssembly](pages/14_기타_클라이언트.md#145-webassembly)



## 5부 — 확장과 생태계

## [제15장: 핵심 확장 활용](pages/15_핵심extension의_활용.md)

### [15.1 Extension 설치](pages/15_핵심extension의_활용.md#151-extension-설치)

### [15.2 httpfs: HTTP/S3 파일 직접 쿼리](pages/15_핵심extension의_활용.md#152-httpfs-https3-파일-직접-쿼리)

### [15.3 AWS / Azure 연동](pages/15_핵심extension의_활용.md#153-aws--azure-연동)

### [15.4 Spatial: 공간 데이터 분석](pages/15_핵심extension의_활용.md#154-spatial-공간-데이터-분석)

### [15.5 Full-Text Search](pages/15_핵심extension의_활용.md#155-full-text-search)

### [15.6 Excel 읽기](pages/15_핵심extension의_활용.md#156-excel-읽기)



## [제16장: 데이터베이스 연동](pages/16_데이터베이스연동.md)

### [16.1 PostgreSQL 연동](pages/16_데이터베이스연동.md#161-postgresql-연동)

### [16.2 MySQL 연동](pages/16_데이터베이스연동.md#162-mysql-연동)

### [16.3 SQLite 연동](pages/16_데이터베이스연동.md#163-sqlite-연동)



## 6부 — 성능 최적화와 실전 운영

## [제17장: 설정과 튜닝](pages/17_설정과튜닝.md)

### [17.1 설정(Configuration) 개요](pages/17_설정과튜닝.md#171-설정configuration-개요)

### [17.2 Pragmas 활용](pages/17_설정과튜닝.md#172-pragmas-활용)

### [17.3 Secrets Manager](pages/17_설정과튜닝.md#173-secrets-manager)



## [제18장: 성능 최적화](pages/18_성능최적화.md)

### [18.1 실행 계획(EXPLAIN) 읽기](pages/18_성능최적화.md#181-실행-계획explain-읽기)

### [18.2 병렬 처리와 메모리 관리](pages/18_성능최적화.md#182-병렬-처리와-메모리-관리)

### [18.3 대용량 데이터 처리 전략](pages/18_성능최적화.md#183-대용량-데이터-처리-전략)



## [제19장: 운영 및 보안](pages/19_운영과보완.md)

### [19.1 Docker로 배포하기](pages/19_운영과보완.md#191-docker로-배포하기)

### [19.2 로깅과 모니터링](pages/19_운영과보완.md#192-로깅과-모니터링)

### [19.3 보안 고려사항](pages/19_운영과보완.md#193-보안-고려사항)

### [19.4 제한(Limits)과 트러블슈팅](pages/19_운영과보완.md#194-제한limits과-트러블슈팅)



## 7부 — 실전 프로젝트

## [제20장: 데이터 분석 파이프라인 구축](pages/20_데이터분석_파이프라인.md)

### [20.1 로컬 데이터 레이크 만들기](pages/20_데이터분석_파이프라인.md#201-로컬-데이터-레이크-만들기)

### [20.2 S3 + Parquet + DuckDB 분석 환경](pages/20_데이터분석_파이프라인.md#202-s3--parquet--duckdb-분석-환경)

### [20.3 실시간 대시보드 연동](pages/20_데이터분석_파이프라인.md#203-실시간-대시보드-연동)



## [제21장: DuckDB로 ML 전처리](pages/21_DuckDB로_ML전처리.md)

### [21.1 대용량 피처 엔지니어링](pages/21_DuckDB로_ML전처리.md#211-대용량-피처-엔지니어링)

### [21.2 Python ML 파이프라인과 통합](pages/21_DuckDB로_ML전처리.md#212-python-ml-파이프라인과-통합)



## [부록](pages/22_부록.md)

### [A. SQL 빠른 참조 (Cheat Sheet)](pages/22_부록.md#a-sql-빠른-참조-cheat-sheet)

### [B. 주요 함수 레퍼런스](pages/22_부록.md#b-주요-함수-레퍼런스)

### [C. 확장 목록과 설치 명령](pages/22_부록.md#c-확장-목록과-설치-명령)
