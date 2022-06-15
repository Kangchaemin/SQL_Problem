### 1. Japan Population: https://www.hackerrank.com/challenges/japan-population/problem
>문제: 
>Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

&nbsp;

> 해설
```
SELECT sum(population) FROM city WHERE countrycode = 'JPN'
```





&nbsp;
### 2. Weather Observation Station 2: https://www.hackerrank.com/challenges/weather-observation-station-2/problem
>문제:  
>Query the following two values from the STATION table:
> - The sum of all values in LAT_N rounded to a scale of  decimal places.
> - The sum of all values in LONG_W rounded to a scale of  decimal places.

&nbsp;

>해설
```
SELECT round(sum(LAT_N), 2) as lat  
     , round(sum(LONG_W), 2) as lon  
FROM station  
```



### 3. Weather Observation Station 18: https://www.hackerrank.com/challenges/weather-observation-station-18/problem
>문제: 
>Consider P1(a, b) and P2(c, d) to be two points on a 2D plane.
> - happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
> - happens to equal the minimum value in Western Longitude (LONG_W in STATION).
> - happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
> - happens to equal the maximum value in Western Longitude (LONG_W in STATION).  
> 
>Query the <b>Manhattan Distance(절대값만 씌우는 거리)</b> between points  and  and round it to a scale of  decimal places.

&nbsp;

>해설

```
SELECT ROUND(ABS(MIN(LAT_N) - MAX(LAT_N)) + ABS(MIN(LONG_W) - MAX(LONG_W)), 4)
FROM STATION;
```




### 4. New Companies: https://www.hackerrank.com/challenges/the-company/problem

>해설

<pre>
-- SELECT C.company_code
--      , C.founder
--      , COUNT(DISTINCT E.lead_manager_code)
--      , COUNT(DISTINCT E.senior_manager_code)
--      , COUNT(DISTINCT E.manager_code)
--      , COUNT(DISTINCT E.employee_code)
-- FROM Company C
--      INNER JOIN Employee E ON C.company_code = E.company_code
     
-- GROUP BY C.company_code, C.founder
-- ORDER BY C.company_code;


SELECT C.company_code
     , C.founder
     , COUNT(DISTINCT LM.lead_manager_code)
     , COUNT(DISTINCT SM.senior_manager_code)
     , COUNT(DISTINCT M.manager_code)
     , COUNT(DISTINCT E.employee_code)
FROM Company C
     LEFT JOIN Lead_Manager LM ON C.company_code = LM.company_code 
     LEFT JOIN Senior_Manager SM ON LM.lead_manager_code = SM.lead_manager_code
     LEFT JOIN Manager M ON SM.senior_manager_code = M.senior_manager_code
     LEFT JOIN Employee E ON M.manager_code = E.manager_code
GROUP BY C.company_code, C.founder
ORDER BY C.company_code
</pre>
