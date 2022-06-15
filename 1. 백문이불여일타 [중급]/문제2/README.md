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







### 4. New Companies: https://www.hackerrank.com/challenges/the-company/problem

