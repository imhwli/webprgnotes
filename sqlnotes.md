## SQL 

- Relational database
- Structure Query Language
- PostgreSQL 

Data Types
- Integer
- Decimal
- Serial
- Varchar
- Timestamp 
- Boolean
- Enum, one of the finite discrete elements


**Creating tables***
~~~
CREATE TABLE flights (
	id SERIAL PRIMARY KEY,
	origin VARCHAR NOT NULL, 
	destination VARCHAR NOT NULL,
	duration INTEGER NOT NULL

);
~~~


> typle /d to show tables in database


***Constraints for individual column***
- NOT NULL
- UNQIUE, no repeat  
- PRIMARY KEY 
- DEFAULT, default value 
- CHECK, condition like only allow value greate than 0 


***Inserting values***
~~~
INSERT INTO flights
	(origin, destination, duration)
	VALUES ('New York', 'London', 415);
~~~


***Selecting values***
~~~
SELECT * FROM flights;

SELECT origin, destination FROM flights;

SELECT * FROM  flights WHERE id = 3;

SELECT * FROM  flights WHERE origin = 'New York';

# use inequality
SELECT * FROM  flights WHERE duration > 500;

# use 
SELECT * FROM  flights WHERE destination = 'Paris' AND duration > 500;

SELECT destination, duration FROM flight;
~~~


***SQL function***
Average, MIN, MAX, SUM, COUNT

~~~
SELECT AVE(duration) FROM flights;
SELECT AVE(duration) FROM flights WHERE origin = 'New York';

SELECT COUNT(*) FROM flight;    <-- return how many row in table
SELECT COUNT(*) FROM flight where origin = 'New York';
~~~


***Select with pattern matching***
~~~
SELECT * FROM flights WHERE origin Like '%a%';
~~~


***Updating Row***
~~~
UPDATE flights 
	SER duration = 430
	WHERE origin = 'New York'
	AND destination = 'London';
~~~


***Deleting row***
~~~
DELETE FROM countries 
	WHERE destination = 'Tokyo';
~~~


***Get certain number of row***
~~~
SELECT * FROM flights LIMIT 2;
~~~

***Sorting column***
~~~
SELECT * FROM flights ORDER BY duration ASC;
~~~


***Group the origins, and then count them. Display the origins and their count***
~~~
SELECT origin, COUNT(*) FROM flights GROUP BY origin;
~~~

~~~
SELECT origin, COUNT(*) FROM flights GROUP BY origin HAVING COUNT(*) > 1;
~~~

***Foreign Key***







































