---
title:  "[SQL] SQL 정리"
excerpt: "SQL 정리하기"

categories:
  - SQL

last_modified_at: 2022-01-13T08:02:00-3:00
toc: true
toc_label: Contents
toc_icon: cog
toc_sticky: true
---

<br />

🚀 <a href="https://programmers.co.kr/learn/challenges" target="_blank">프로그래머스 SQL 문제풀기</a>🚀

<br />

어린 동물 찾기 

```sql
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE INTAKE_CONDITION != "Aged"
```

```sql
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE not INTAKE_CONDITION = "Aged"
```

<br />

여러기준으로 정렬하기

```sql
SELECT ANIMAL_ID, NAME, DATETIME
FROM ANIMAL_INS
ORDER by NAME , DATETIME DESC
```

<br />

```sql
-- 코드를 입력하세요
SELECT NAME 
FROM ANIMAL_INS 
ORDER by DATETIME 
LIMIT 1
```

<br />

```sql
-- 코드를 입력하세요
SELECT DATETIME as "시간"
FROM ANIMAL_INS
ORDER by DATETIME
LIMIT 1
```

<br />

```sql
-- 코드를 입력하세요
SELECT count(*)
FROM ANIMAL_INS

```

<br />

```sql
-- 코드를 입력하세요
SELECT count(DISTINCT NAME)
FROM ANIMAL_INS
```

<br />

```sql
-- 코드를 입력하세요
SELECT ANIMAL_TYPE , count(*) as "count"
FROM ANIMAL_INS
order by ANIMAL_TYPE
GROUP by ANIMAL_TYPE
```

<br />

```sql
-- 코드를 입력하세요
SELECT NAME, count(NAME)
FROM ANIMAL_INS
GROUP BY NAME
HAVING count(NAME)> 1
ORDER BY NAME
```

<br />

```sql
SELECT HOUR(DATETIME), count(*)
FROM ANIMAL_OUTS
WHERE HOUR(DATETIME) BETWEEN 9 and 19
GROUP BY HOUR(DATETIME)
ORDER BY HOUR(DATETIME)
```

<br />

입양 시각 구하기(2)

```sql
-- 코드를 입력하세요
 
WITH RECURSIVE COUNTER(HOUR) AS ( 
    SELECT 0 #비반복문
    UNION ALL #UNION 구문
    SELECT HOUR + 1 FROM COUNTER WHERE HOUR < 23 #recursive 구문 
)


SELECT HOUR, COUNT(A.ANIMAL_ID) AS COUNT
FROM COUNTER as C LEFT JOIN 
        ANIMAL_OUTS A ON C.HOUR = HOUR(A.DATETIME)
GROUP BY HOUR
ORDER BY HOUR
```

<br />

이름이 없는 동물의 아이디

```sql
-- 코드를 입력하세요
SELECT ANIMAL_ID
FROM ANIMAL_INS
WHERE name is null
```

```sql
-- 코드를 입력하세요
SELECT ANIMAL_ID
FROM ANIMAL_INS
WHERE NAME is not null
```

<br />



```sql
-- 코드를 입력하세요
SELECT ANIMAL_TYPE,(CASE WHEN NAME is null then "No name" else NAME END) as NAME, SEX_UPON_INTAKE
FROM ANIMAL_INS
ORDER BY ANIMAL_ID
```





없어진 기록 찾기

```sql
-- 코드를 입력하세요
SELECT B.ANIMAL_ID, B.NAME
FROM  ANIMAL_INS A Right JOIN ANIMAL_OUTS B ON A.ANIMAL_ID = B.ANIMAL_ID
WHERE A.ANIMAL_ID is null
ORDER BY ANIMAL_ID
```



있었는데요 없었습니다

```sql
-- 코드를 입력하세요
SELECT A.ANIMAL_ID, A.NAME
FROM ANIMAL_INS A right Join ANIMAL_OUTS B on A.ANIMAL_ID = B.ANIMAL_ID
WHERE A.DATETIME > B.DATETIME
ORDER BY A.DATETIME
```



오랜기간 보호한 동물

```sql
-- 코드를 입력하세요
SELECT A.NAME, A.DATETIME
FROM ANIMAL_INS A left Join ANIMAL_OUTS B on A.ANIMAL_ID = B.ANIMAL_ID
WHERE B.ANIMAL_ID is null -- 입양이 못가야 하니깐 테이블에서 비워져야 한다. 
ORDER BY A.DATETIME
limit 3
```

보호소에서 중성화한 동물

```sql
-- 코드를 입력하세요
SELECT B.ANIMAL_ID, B.ANIMAL_TYPE,B.NAME
FROM ANIMAL_INS A inner JOIN ANIMAL_OUTS B on A.ANIMAL_ID = B.ANIMAL_ID
WHERE (A.SEX_UPON_INTAKE like "Intact%") 
and ((B.SEX_UPON_OUTCOME like "Neutered%") or ( B.SEX_UPON_OUTCOME like "Spayed%"))
```



이름이 el 들어가는 동물 찾기

```sql
-- 코드를 입력하세요
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE NAME like "%el%" and ANIMAL_TYPE like "DOG"
ORDER BY NAME
```



중성화 여부 확인하기

```sql
-- 코드를 입력하세요
SELECT ANIMAL_ID, NAME, (case when SEX_UPON_INTAKE like "Intact%" then 
                     'X' else 'O' end) as "중성화"
FROM ANIMAL_INS
ORDER BY ANIMAL_ID
```



오랜 기간 보호한 동물

```sql
-- 코드를 입력하세요
SELECT B.ANIMAL_ID, B.NAME
FROM ANIMAL_INS A RIGHT JOIN ANIMAL_OUTS B on A.ANIMAL_ID = B.ANIMAL_ID
ORDER BY B.DATETIME - A.DATETIME DESC
LIMIT 2
```



Date로 형변환

```sql
SELECT ANIMAL_ID, NAME, date_format(DATETIME, '%Y-%m-%d') as "날짜" #ymd가 대문자랑 소문자랑 결과값이 다름.
FROM ANIMAL_INS
```

