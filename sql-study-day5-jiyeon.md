### 필요한 데이터만 출력하는 WHERE절
특정 조건을 기준으로 원하는 행을 출력하는데 사용
```SQL
-- EMP테이블에서 DEPTNO가 30인 데이터만 출력
SELECT *
   FROM EMP
 WHERE DEPTNO = 30; 
```
> WHERE절이 포함된 SELECT문을 실행하면 조회할 테이블의 각 행에    
> WHERE절의 조건식을 대입하여 결과가 '참'인 경우에만 출력된다.

### 여러 개 조건식을 사용하는 AND, OR 연산자
```SQL
-- EMP테이블에서 DEPTNO가 30 이거나, JOB이 'CLERK'인 데이터 출력하기
SELECT *
   FROM EMP
  WHERE DEPTNO = 30
    OR JOB = 'CLERK';
    
-- EMP테이블에서 DEPTNO가 30 이고, JOB이 'SALESMAN'인 데이터 출력하기   
SELECT *
   FROM EMP
 WHERE DEPTNO = 30
   AND JOB = 'SALESMAN';
```
> 실무에서는 다양한 조건을 한번에 만족시키는 데이터만을 추출해야 할 때가 많기 때문에    
> AND 연산자를 더 많이 사용하는 경향이 있다.
