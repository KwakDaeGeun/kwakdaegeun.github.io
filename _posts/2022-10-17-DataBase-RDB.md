---
layout: single
categories:
 - oracle
title:  "[Oracle] 관계형 데이터베이스"
---

### 릴레이션

![image](https://user-images.githubusercontent.com/113850146/197397478-5936cf41-4c4d-4470-af37-660ed0524328.png)

- 속성 - 필드, 컬럼

- 릴레이션을 구성하는 각 열(Column)의 이름

- 튜플 - 레코드, 행 

- 릴레이션의 각 행

![image](https://user-images.githubusercontent.com/113850146/197397629-c08197fd-8a90-4be8-8fb5-304c75cd0ca6.png)

### 테이블

- 중복된 레코드가 존재하지 않는다.

- 레코드간의 순서는 의미가 없다.

- 레코드 내에서 필드의 순서는 의미가 없다.

- 모든 필드는 원자값을 가진다.


### 키

- 필드들의 일부로 각 레코드들을 유일하게 식별해낼 수 있는 식별자.

- 일반적으로 하나의 필드를 지정하여 키로 지정하나, 여러 개의 필드들로 키를 구성할 수도 있다.

- 레코드간의 순서가 의미가 없으므로 레코드를 구분하기 위해서는 각 레코드의 값을 이용한다.

#### 슈퍼키

- 아무런 제약 조건 없이 레코드를 식별할 수 있는 필드의 집합

#### 후보키

-  튜플들을 구별하는 데 기준이 되는 하나 또는 그 이상의 필드 집합

### 기본키(Primary Key)

- 후보키 중에서 식별자로 정의한 하나의 키

- 속성이 항상 고유한 값을 가져야한다.

- 값이 변경될 가능성이 높은 속성은 기본키로 선정하지 않는것이 좋다.

- 테이블에 기본키는 1개만 만들 수 있다.

- 널(NULL) 값을 가질 수 없다.

### 외래키(Foreign Key)

- 다른 테이블의 기본키를 참조하는 필드 집합

![image](https://user-images.githubusercontent.com/113850146/197398332-399d076c-a000-4dd7-8dcc-97dd28ffd599.png)


## 데이터 딕셔너리

- 관계형 데이터베이스에서 객체를 정의하게 되면 그 객체가 가진 메타 데이터의 정보가 저장되는 곳.

- 사용자에 의해서 추가,삭제,수정되지 못하며 오로지 오라클 시스템에 의해서만 가능.

- ex)

```sql
SELECT * FROM TAB; 
-- TAB 는 TABLE의 약자.
```

### DESC
- 테이블에서 데이터를 조회하기 위해서는 테이블의 구조를 알아야 한다.

- 테이블의 구조를 확인하기 위한 명령어로는 DESC가 있다.

- 형식  :
  
```sql
DESC 테이블명
```

![image](https://user-images.githubusercontent.com/113850146/197398716-01084618-0c05-422a-9e8d-8924996623ce.png)

- DESC 명령어는 테이블의 컬럼 이름, 데이터 형, 길이와 NULL 허용 유무 등과 같은 특정 테이블의 정보를 알려준다.

### 오라클의 데이터 형

- NUMBER : 숫자 데이터 저장

- DATE : 세기, 년, 월, 일, 시간, 분, 초의 날자 및 시간 데이터를 저장.

- CHAR : 고정 길이 문자 데이터를 저장하기 위한 자료형.

![image](https://user-images.githubusercontent.com/113850146/197398908-7c341297-6b40-488a-878d-c7576afbb45c.png)

- VARCHAR2 : 가변 길이 문자 데이터를 저장하기 위한 자료형

![image](https://user-images.githubusercontent.com/113850146/197398920-bbea8d21-5e2b-4f92-b342-3b3d4ef4b0f4.png)

### SELECT

- 데이터를 조회하기 위한 SQL 명령어.

- 형식  :  

```sql
SELECT [DISTINCT] {*, column[Alias]} FROM 테이블명;
```

### 산술 연산자

![image](https://user-images.githubusercontent.com/113850146/197399049-53cd5feb-6af2-45db-86d5-c6538f81b0e7.png)

### NULL

- 데이터 베이스에서 NULL은 중요한 데이터이다.

- NULL을 제대로 이해하지 못하고 쿼리문을 작성시 원하지 않은 결과를 얻을 수 있다.

### NVL
- NULL을 0또는 다른 값으로 변환하기 위하여 NVL함수를 제공한다.

- 형식  : 

```sql
SELECT nvl(column,0)  FROM 테이블명;
```

### 별칭

- 원래의 컬럼명 대신 원하는 컬럼명으로 출력하고자 하는 구문 컬럼 뒤에 AS(alias) 라는 키워드를 쓴 후 별칭을 기술하여 출력

### Concatenation 연산자

- 오라클에서 여러개의 컬럼을 연결할 때 사용하는 Concatenation 연산자로 "\|\|" 수직바를 사용한다.

- 형식  : 

```sql
SELECT column1 || column2 FROM 테이블명;
```

### DISTINCT 키워드

- 중복을 제거하는 키워드이다.

- 형식  : 

```sql
SELECT DISTINCT column FROM 테이블명;
```



