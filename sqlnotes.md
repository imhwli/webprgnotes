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
- Read GROUP BY first
~~~
SELECT origin, COUNT(*) FROM flights GROUP BY origin;
~~~

~~~
SELECT origin, COUNT(*) FROM flights GROUP BY origin HAVING COUNT(*) > 1;
~~~

***Foreign Key***

- Creating new passage tables
- REFERENCE keywaord create link between the two tables 
- THe REFERENCE keyword reinforce constraint and prevent user from breaking it. 
~~~
CREATE TABLE passengers (
	id SERIAL PRIMARY KEY,
	name VARCHAR NOT NULL,
	flight_id INTEGER REFERENCES flights
	);
~~~

***Joining Tables***
~~~
SELECT origin, destination, name FROM flights JOIN passengers 
	ON passenger.flight_id = flights.id;

SELECT origin, destination, name FROM flights JOIN passengers 
	ON passenger.flight_id = flight.id WHERER name = 'Alice';
~~~


> LEFT and RIGHT JOIN. It includes element in left or right along with the intersection. 


***Create Index***
- Indexing for query/lookup faster
- Trade off between faster lookup and updating data. Update data mean update the indexing as well  

***Nested Query***
~~~
SELECT flight_id FROM passengers GROUP BY flight_id HAVING COUNT(*) > 1;

// Nesting query
SELECT * FROM flight WHERE id IN (SELECT flight_id FROM passengers GROUP BY flight_id HAVING COUNT(*) > 1);
~~~



***SQL Injection***
- Use placeholder from SQLalchemy instead of string concatentation to avoid SQL injection
~~~
SELECT * FROM users 
	WHERE (username = 'username')
	AND (password = 'password');

SELECT * FROM users 
	WHERE (username = 'hacker')
	AND (password = '1' OR '1' = '1');
~~~


***Race Conditions***
~~~
SELECT balance FROM bank where user_id = 1; 

UPDATE bank 
	SET balance = balance - 100
	WHERE user_id = 1;
~~~

> First check the account balance to make sure it has $100. Then withdraw. 
> If two select statements are ran simutaneoutly and then two update statements following them are valid to run. This can cause race condition problem. 

Transaction - sequence of command and locking the database, prevent other from changing the database until it finish its transaction. 



***Database Engine***
- Database engine - handle the connection and the queryto database
- Environment variable - variable that exist in the terminal environment. 

Printing out database contents
~~~
import os 

from sqlalchemy import create_engine
from sqlalchemy.orm import scoped_session, sessionmaker

engine =create_engine(os.getenv("DATABASE_URL"))
db = scoped_session(sessionmaker(bind=engine))

def main():
	flights= db.execute("SELECT origin, destination, duration FROM flights").fetchall()
	for flight in flights:
		print(f"{flight.origin} to {flight.destination}, {flight.duration} minutes.")

if __name__ == "__main__":
	main()

~~~































