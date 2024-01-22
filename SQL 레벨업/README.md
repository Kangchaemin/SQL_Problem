## 1. Address테이블에서 성별 별로 나이 순위(넌너뛰기 있게)를 매기는 SELECT 구문 작성.
<pre>
  SELECT name, sex, age, 
         RANK() OVER(PARTITION BY sex ORDER BY age DESC) rnk_desc
    FROM Address
</pre>
![22](https://github.com/Kangchaemin/SQL_Problem/assets/43837994/53aeb378-7521-45ba-a3e0-61d90dd2a48b)


