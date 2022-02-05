### Conceptual Exercise

Answer the following questions below:

- What is PostgreSQL?
  A relational database system

- What is the difference between SQL and PostgreSQL?
  PostgreSQL is a relational database system that uses SQL, a querying language to pull data

- In `psql`, how do you connect to a database?
  You can connect to a database using a command like: ```\c DATABASE_NAME```

- What is the difference between `HAVING` and `WHERE`?
  HAVING is used when you want to filter the results of a query using GROUP BY. 

- What is the difference between an `INNER` and `OUTER` join?
  An INNER join only keeps values that both tables have. The OUTER join keeps all values from the first table. 

- What is the difference between a `LEFT OUTER` and `RIGHT OUTER` join?
  A left outer join query will include all the results in the left table. A right outer join will keep all the results in the right table. If the other table does not have matching values in the join column, they will not be included.

- What is an ORM? What do they do?
  ORM stands for object relational mapper, and it maps tables and relationships through objects.

- What are some differences between making HTTP requests using AJAX 
  and from the server side using a library like `requests`?\
  When making requests from the server side, the page will need to be refreshed to see the results. When making requests using AJAX, the webpage does not have to reload, and can just manipulate the DOM to update.

- What is CSRF? What is the purpose of the CSRF token?
CSRF stands for cross site request forgery, and is a type of attack where users end up sending malicious requests to sites that they are authorized by. The CSRF token is a randomly generated value that validates the user's submitted forms. This prevents attackers from making malicious requests since they lack all the information needed to make a request.

- What is the purpose of `form.hidden_tag()`?
  The purpose of is to include the CSRF value along with the form's submission.