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

~~~



























