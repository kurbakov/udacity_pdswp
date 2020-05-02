## Here are my solutions for Practice Quiz 1 questions:

<b>Question 1</b>: Query that creates a table with the following details: actor's first and last name combined as full_name, film title and length of the movies.

```sql
  SELECT a.first_name, 
         a.last_name,
         a.first_name || ' ' || a.last_name AS full_name,
         f.title,
         f.length
  FROM   film_actor fa
  JOIN   actor a
  ON     fa.actor_id = a.actor_id
  JOIN   film f
  ON     f.film_id = fa.film_id
```

<b>Question 2</b>: Write a query that creates a list of actors and movies where the movie length was more than 60 minutes.

```sql
  SELECT a.first_name, 
         a.last_name,
         a.first_name || ' ' || a.last_name AS full_name,
         f.title ,
         f.length
  FROM   film_actor fa
  JOIN   actor a
  ON     fa.actor_id = a.actor_id
  JOIN   film f
  ON     f.film_id = fa.film_id
  WHERE  f.length > 60
```

<b>Question 3</b>: Write a query that captures the full name of the actor, and counts the number of movies each actor has made. Identify the actor who has made the maximum number of movies.

```sql
  SELECT actorid, full_name, 
         COUNT(filmtitle) film_count_peractor
  FROM
      (SELECT a.actor_id actorid,
              a.first_name, 
              a.last_name,
              a.first_name || ' ' || a.last_name AS full_name,
              f.title filmtitle
      FROM    film_actor fa
      JOIN    actor a
      ON      fa.actor_id = a.actor_id
      JOIN    film f
      ON      f.film_id = fa.film_id) t1
  GROUP BY 1, 2
  ORDER BY 3 DESC
```