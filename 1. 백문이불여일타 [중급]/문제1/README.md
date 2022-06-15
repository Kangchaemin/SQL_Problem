### 1. Leetcode 595. Big Countries: https://leetcode.com/problems/big-countries/
>문제:  
>A country is big if:
> - it has an area of at least three million (i.e., 3000000 km2), or
> - it has a population of at least twenty-five million (i.e., 25000000). 
>  
> Write an SQL query to report the name, population, and area of the big countries.  
> Return the result table in any order.  

&nbsp;

> 해설  

SELECT name, population, area  
FROM world  
WHERE area >= 3000000 OR population >= 25000000  




&nbsp;
### 2. Leetcode 620. Not Boring Movies: https://leetcode.com/problems/not-boring-movies/
>문제:   
>Write an SQL query to report the movies with an odd-numbered ID and a description that is not "boring".  
>Return the result table ordered by rating in descending order.

&nbsp;

>해설  

SELECT *  
FROM Cinema  
<b> WHRER mod(id, 2) != 0 AND description not like 'boring' # description != 'boring'</b>  
ORDER BY rating desc  

&nbsp;





### 3. Leetcode 182. Duplicate  Emails: https://leetcode.com/problems/duplicate-emails/
>문제:  
>Write an SQL query to report all the duplicate emails.  

&nbsp;

>해설  

SELECT email  
FROM person  
GROUP BY email  
<b> HAING COUNT(id) >= 2 </b> 






&nbsp;
### 4. Leetcode 175. Combine Two Tables: https://leetcode.com/problems/combine-two-tables/
>문제:  
>Write an SQL query to report the first name, last name, city, and state of each person in the Person table.  
>If the address of a personId is not present in the Address table, report null instead.  

&nbsp;

>해설  

SELECT firstName, lastName, city, state  
FROM Person  
<b> LEFT JOIN Address ON Person.personId = Address.personId </b>
