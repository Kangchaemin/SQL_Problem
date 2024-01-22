## 1. Address테이블에서 성별 별로 나이 순위(넌너뛰기 있게)를 매기는 SELECT 구문 작성.
<pre>
  SELECT name, sex, age, 
         RANK() OVER(PARTITION BY sex ORDER BY age DESC) rnk_desc
    FROM Address
</pre>
![22](https://github.com/Kangchaemin/SQL_Problem/assets/43837994/53aeb378-7521-45ba-a3e0-61d90dd2a48b)

* * *
## 2. 윈도우 함수 ROW_NUMBER에서 ORDER BY시 조건을 하나 더 넣어줘야 하는 이유
![22](https://github.com/Kangchaemin/SQL_Problem/assets/43837994/3d3feb49-30c1-4395-bc58-f3a955ac6a56)
![33](https://github.com/Kangchaemin/SQL_Problem/assets/43837994/6acf2bff-e720-47e2-8a2d-25e567d9473a)

정렬 키를 체중(weight) 필드로만 지정하면, hi와 lo를 산출할 때 **같은 체중의 학생들이 언제나 같은 순서로 정렬된다는 보장이 없기 때문입니다.**  
weight필드 값이 같을때 **어떤 순서로 정렬할지 보장하지 않으므로** 물리적인 기록 순서에 따라 순서가 바뀌기 때문에 환경에 따라 다른 결과가 나올 수도 있다.  
