Make sure you download the starter code and run the following:

```sh
  psql < movies.sql
  psql movies_db
```

In markdown, you can place a code block inside of three backticks (```) followed by the syntax highlighting you want, for example

\```sql

SELECT \* FROM users;

\```

Using the `movies_db` database, write the correct SQL queries for each of these tasks:

1.  The title of every movie.
    ```sql
    SELECT title
    FROM movies;
    ```
	
1.  All information on the G-rated movies.
    ```sql
    SELECT id, title, release_year, runtime, rating, studio_id
    FROM movies
    where rating = 'G';
    ```

2.  The title and release year of every movie, ordered with the
    oldest movie first.
    ```sql
    SELECT id, title, release_year
    FROM movies
    ORDER BY release_year;
    ```
    
3.  All information on the 5 longest movies.
    ```sql
    SELECT id, title, release_year, runtime, rating, studio_id
    FROM movies
    order by runtime desc
    limit 5;
    ```
	
4.  A query that returns the columns of `rating` and `total`, tabulating the
    total number of G, PG, PG-13, and R-rated movies.
    ```sql
    select rating, count(id) as total
    from movies
    group by rating
    ```

5.  A table with columns of `release_year` and `average_runtime`,
    tabulating the average runtime by year for every movie in the database. The data should be in reverse chronological order (i.e. the most recent year should be first).
    ```sql
    select release_year, avg(runtime)
    from movies
    group by release_year
    order by release_year desc
    ```

6.  The movie title and studio name for every movie in the
    database.
    ```sql
    SELECT title, name as studio_name
    FROM movies left join studios on movies.studio_id = studios.id;
    ```

7.  The star first name, star last name, and movie title for every
    matching movie and star pair in the database.
    ```sql
    select first_name, last_name, title
    from movies 
        inner join roles on movies.id = roles.movie_id
        left join stars on roles.star_id = stars.id
    ```
	
8.  The first and last names of every star who has been in a G-rated movie. The first and last name should appear only once for each star, even if they are in several G-rated movies. *IMPORTANT NOTE*: it's possible that there can be two *different* actors with the same name, so make sure your solution accounts for that.
    ```sql
    select distinct first_name, last_name
    from movies 
        inner join roles on movies.id = roles.movie_id
        left join stars on roles.star_id = stars.id
    where rating = 'G'
    ```

9.  The first and last names of every star along with the number
    of movies they have been in, in descending order by the number of movies. (Similar to #9, make sure
    that two different actors with the same name are considered separately).
    ```sql
    select distinct first_name, last_name
    from movies 
        inner join roles on movies.id = roles.movie_id
        left join stars on roles.star_id = stars.id
    where rating = 'G'
    ```
    
### The rest of these are bonuses

11. The title of every movie along with the number of stars in
    that movie, in descending order by the number of stars.

12. The first name, last name, and average runtime of the five
    stars whose movies have the longest average.

13. The first name, last name, and average runtime of the five
    stars whose movies have the longest average, among stars who have more than one movie in the database.

14. The titles of all movies that don't feature any stars in our
    database.

15. The first and last names of all stars that don't appear in any movies in our database.

16. The first names, last names, and titles corresponding to every
    role in the database, along with every movie title that doesn't have a star, and the first and last names of every star not in a movie.
