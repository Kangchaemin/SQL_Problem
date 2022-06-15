### 1. Weather Observation Station 3: https://www.hackerrank.com/challenges/weather-observation-station-3/problem
>문제:  
>Query a list of CITY names from STATION for cities that have an even ID number.  
>Print the results in any order, but exclude duplicates from the answer.

&nbsp;

>해설 

```
SELECT DISTINCT(CITY)
FROM STATION
WHERE MOD(ID, 2) = 0
```


&nbsp;
### 2. Weather Observation Station 19: https://www.hackerrank.com/challenges/weather-observation-station-19/problem
>문제:  
>Consider P1(a, c) and P2(b, d) to be two points on a 2D plane where (a, b) are the respective minimum and maximum values of Northern Latitude (LAT_N)  
>and (c, d) are the respective minimum and maximum values of Western Longitude (LONG_W) in STATION.  
>Query the <b>Euclidean Distance(루트 씌우는거리)</b> between points P1 and P2 and format your answer to display 4 decimal digits.

&nbsp;

>해설:

<pre>
<b>SELECT ROUND(SQRT(POWER(MIN(LAT_N) - MAX(LAT_N), 2) + POWER(MIN(LONG_W) - MAX(LONG_W), 2)), 4)</b>
FROM STATION;

-- POWER(MIN(LAT_N) - MAX(LAT_N), 2)
-- POWER(MIN(LONG_W) - MAX(LONG_W), 2)
</pre>


&nbsp;
### 3. Placements: https://www.hackerrank.com/challenges/placements/problem
> 해설

<pre>
SELECT S.name
FROM Friends F
     INNER JOIN Students S ON F.ID = S.ID
     -- Packages Table Join twice
     <b>INNER JOIN Packages P1 ON P1.ID = F.ID
     INNER JOIN Packages P2 ON P2.ID = F.Friend_ID</b>
WHERE P1.Salary < P2.Salary
ORDER BY P2.Salary
</pre>



&nbsp;
### 4. Binary Tree Nodes: https://www.hackerrank.com/challenges/binary-search-tree-1/problem
>해설

<pre>
-- root: no parent node

SELECT DISTINCT BST.N
<b>     , CASE 
            WHEN BST.P IS NULL THEN 'Root'
            WHEN BST2.N IS NULL THEN 'Leaf'
            ELSE 'Inner'
       END</b>
FROM BST
     <b>LEFT JOIN BST AS BST2 ON BST.N = BST2.P</b>
     
ORDER BY BST.N
</pre>
