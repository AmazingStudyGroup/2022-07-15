### 실습용 테이블 살펴보기

```sql
--DESC 테이블명;
DESC EMP;
```
> - byte의 크기와 문자의 관계   
> 10byte = 한글(2byte) 5글자 = 영문(1byte) 10글자

### 데이터를 조회하는 3가지 방법 - SELECTION, PROJECTION, JOIN
데이터베이스에 보관되어 있는 데이터를 조회하는데 사용하는 SELECT문은 출력데이터를 선정하는 방식에 따라
크게 세 가지 방식으로 나뉨
- SELECTION    
특정 행만 선별하여 조회하는 방식
- PROJECTION     
특정 열만 선별하여 조회하는 방식
- JOIN    
두 개 이상의 테이블을 옆으로 연결하여 하나의 테이블처럼 데이터를 조회하는 방식

### SQL의 기본 뼈대, SELECT절과 FROM절
```SQL
-- SELECT 조회할 열1 이름, 열 2 이름, ...
--    FROM 조회할 테이블 이름

-- 테이블 전체 열 조회
SELECT * FROM EMP;

-- 특정(사원번호, 부서번호) 열 조회
SELECT EMPNO, DEPTNO
   FROM EMP;
```
### 중복 데이터를 삭제하는 DISTINCT
```SQL
-- 열 이름 앞에 DISTINCT 사용하여 중복 제거
SELECT DISTINCT DEPTNO
   FROM EMP;

-- ALL로 중복되는 열 제거없이 그대로 출력
-- SELECT JOB, DEPTNO FROM EMP; 와 같음
SELECT ALL JOB, DEPTNO
   FROM EMP;
```
### 한눈에 보기 좋게 alias 설정하기
```SQL
-- SAL열을 활용한 연산을 통해 '연간 총 수입' 열을 만든다
-- 열 이름을 정하지 않을 경우, 연산식이 그대로 노출되기 때문에 별칭을 정해준다.
SELECT ENAME, SAL, SAL*12+COMM AS ANNSAL, COMM
   FROM EMP;
```

### 원하는 순서로 출력 데이터를 정렬하는 ORDER BY
> ORDER BY 절은 SELECT문을 작성할 때, 사용할 수 있는 여러 절 중 **가장 마지막 부분**에 쓴다.
```SQL
SELECT 조회할 열1 이름, 열2 이름, ...
  FROM 조회할 테이블 이름
  .
  .
  .
ORDER BY 정렬하려는 열 이름 (정렬옵션)
```
```SQL
--오름차순
SELECT *
  FROM EMP
ORDER BY SAL;
--내림차순
SELECT *
  FROM EMP
ORDER BY DESC;
-- 동시에 사용
SELECT * 
  FROM EMP
ORDER BY DEPTNO ASC, SAL DESC;
```
> ORDER BY절 사용시 주의사항     
> 정렬은 시간이 걸리는 작업이기 때문에 꼭 필요한 경우가 아니면 사용하지 않는 것이 좋다.
