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



### 10월 27일

Length() : 문자의 길이를 알려주는 함수

```mysql
select * from dsmdb.student where  6 >=  length(NAME);
```



Substr() : 글에서 글자를 찾아주는 함수

```mysql
select substr('동해물과 백두산이',2,5);
```



Concat() : 문자를 붙여주는 함수

```mysql
select concat(SNO, ' ',NAME) AS STUDENT from dsmdb.student;
```



Ifnull() : 칼럼이름에 CLUB_NO의 null 값을 '없다'로 바꿔주는 함수

```mysql
select SNO,NAME, IFNULL(CLUB_NO,'없다') AS '칼럼이름' from dsmdb.student where CLUB_NO is null;
```



like() : 글중에 글자가 있는지 확인해 주는 함수 %는 갯수상관없이 _는 하나만

```mysql
select * from dsmdb.student where name like '이%' and name like '%호%';
```



Count : 칼럼 내용의 캐수를 알려주는 함수

+ group by 는 중복되는 내용을 하나로 묶어주는것

```mysql
select SYEAR, Count(SYEAR) from dsmdb.student group by SYEAR order by SYEAR;
```

1. 교실 2학년 4반을 사용하는 전공동아리 명과 동아리명 길이를 출력하시오.

   ```mysql
   select distinct CLUB_NM,length(CLUB_NM) from dsmdb.major_club where PLC='교실(2-4)';
   ```

2. 본인의 학급을 출력하시오

   ```mysql
   select name as 이름, concat(syear, '학년 ',cls,'반')as 학급 from dsmdb.student where NAME='한준호'
   ```