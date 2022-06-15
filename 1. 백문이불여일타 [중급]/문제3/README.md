### 1. Population Density Difference: https://www.hackerrank.com/challenges/population-density-difference/problem
>문제:  
>Query the difference between the maximum and minimum populations in CITY.

&nbsp;

>해설  

```
SELECT MAX(population) - MIN(population)
FROM CITY;
```


&nbsp;
### 2. Weather Observation Station 11: https://www.hackerrank.com/challenges/weather-observation-station-11/problem
>문제:  
>Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels.  
>Your result cannot contain duplicates.


&nbsp;

>해설:

<pre>
SELECT DISTINCT CITY
FROM STATION
<b>WHERE LEFT(CITY, 1) NOT IN ('A', 'E', 'I', 'O', 'U')
      OR RIGHT(CITY, 1) NOT IN ('A', 'E', 'I', 'O', 'U');</b>
</pre>





&nbsp;
### 3. Weather Observation Station 13: https://www.hackerrank.com/challenges/weather-observation-station-13/problem
>문제:  
>Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38,7880 and less than 137,2345.  
>Truncate your answer to  decimal places.

&nbsp;

>해설:

<pre>
SELECT TRUNCATE(SUM(LAT_N), 4)
FROM STATION
-- WHERE LAT_N BETWEEN(38.7880, 137.2345);
-- greater than, less than은 범위에서 제외시켜야한다. 
<b>WHERE LAT_N > 38.7880 AND LAT_N < 137.2345;</b>
</pre>





&nbsp;
### 4. Top Competitors: https://www.hackerrank.com/challenges/full-score/problem

>해설

<pre>
-- select *
-- from Submissions
-- inner join Challenges on submission.challenge_id = Challenges.challenge_id;

-- select s.challenge_id, s.score, c.difficulty_level, d.score
-- from Submissions s, Challenges c, Difficulty d
-- where s.challenge_id = c.challenge_id AND d.difficulty_level = c.difficulty_level;


SELECT h.hacker_id, h.name 
FROM Submissions s, Challenges c, Difficulty d, Hackers h
WHERE s.challenge_id = c.challenge_id AND
      d.difficulty_level = c.difficulty_level AND
      h.hacker_id = s.hacker_id AND
      s.score = d.score
      
GROUP BY h.hacker_id, h.name
HAVING COUNT(DISTINCT s.submission_id) > 1

ORDER BY COUNT(DISTINCT s.submission_id) desc, h.hacker_id;
</pre>
