# DataBase Study

### 10월 6일

1번째 쿼리

+ country 테이블에서 name이 S로 시작하고 인구수가 1천만명이상인 나라를 인구수 기준 내림차순으로 나타내라

```mysql
SELECT *
  FROM WORLD.COUNTRY
 WHERE POPULATION >= 10000000 AND NAME LIKE  'S%'
 ORDER BY POPULATION DESC; 
```

2번째 쿼리

+ country 테이블에서 CONTINENT가 ASIA이고, LIFEEXPECTANCY가 70세 이상인 나라를 나타내라

```mysql
SELECT *
  FROM WORLD.COUNTRY
 WHERE CONTINENT = 'ASIA' AND LIFEEXPECTANCY >= 70
```

3번째 쿼리

+ country 테이블에서 GNP가 300000이상이거나, CODE가 B로 시작하는 것을 나타내라

```MYSQL
SELECT *
  FROM WORLD.COUNTRY
 WHERE GNP >= 300000 OR CODE LIKE 'K%'
```

