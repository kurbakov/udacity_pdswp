## Workspace

We have provided a Workspace at the bottom of this page for you to run your queries. Please feel free to use it to write your queries, run them, and export the data to a .csv file.


## What are the Question Sets?

We have also provided a set of questions that you are free to consider and include in your Project Submission. These are solely provided for your convenience, and you can choose to use any of the questions in these sets or none at all in your project submission.

<b>
If you are unsure what queries to generate (for e.g., what kind of query will require the use of Window Functions), we strongly recommend using questions from the question set.
</b>

## Question 1

We want to understand more about the movies that families are watching. The following categories are considered family movies: Animation, Children, Classics, Comedy, Family and Music.

<b>
Create a query that lists each movie, the film category it is classified in, and the number of times it has been rented out.
</b>

## Check Your Solution

For this query, you will need 5 tables: Category, Film_Category, Inventory, Rental and Film. Your solution should have three columns: Film title, Category name and Count of Rentals.

The following table header provides a preview of what the resulting table should look like if you order by category name followed by the film title.

HINT: One way to solve this is to create a count of movies using aggregations, subqueries and Window functions.


<img src="img/ques1a.png">


## Question 2

Now we need to know how the length of rental duration of these family-friendly movies compares to the duration that all movies are rented for. <b>Can you provide a table with the movie titles and divide them into 4 levels (first_quarter, second_quarter, third_quarter, and final_quarter) based on the quartiles (25%, 50%, 75%) of the rental duration for movies across all categories?</b> Make sure to also indicate the category that these family-friendly movies fall into.

## Check Your Solution

The data are not very spread out to create a very fun looking solution, but you should see something like the following if you correctly split your data. You should only need the category, film_category, and film tables to answer this and the next questions. 

HINT: One way to solve it requires the use of percentiles, Window functions, subqueries or temporary tables.

<img src="img/ques2a.png">


## Question 3

Finally, provide a table with the family-friendly film category, each of the quartiles, and the corresponding count of movies within each combination of film category for each corresponding rental duration category. The resulting table should have three columns:

- Category
- Rental length category
- Count

## Check Your Solution

The following table header provides a preview of what your table should look like. The Count column should be sorted first by Category and then by Rental Duration category.

HINT: One way to solve this question requires the use of Percentiles, Window functions and Case statements.

<img src="img/ques3a.png">