## Scalability 

***Vertical scaling***
- add more resources to current server

***Horizontal scaling***
- add more server


***Load Balancing Algorithm*** 
- Round robin 
- random choice
- fewest connections
- and more 


Session-aware load balancing 
- sticky session 
- sessions in database - regardless of which webserver user connect to 
- client side session - storing session data in client 


Autoscaling 
- horizontal scaling adding ro remove servers depends on traffic


Load balancer receive heartbeat signal from the server


Flask 
- session directory - for storing session
- 


cookies 
Signing certificate 


Database Partitioning 
- spliting tables into multiple tables - for more efficient query

Vertical partitioning 
- for table getting too many columns
- split the columns into different tables




Horizontal partitioning 
- For table getting to row, 
- split the row into different tables
- Added complexity - need to decide which table to query 
- schema changed


Database sharding
- rather than partitioning tables, spliting database into multiple server
- but the draw back is when joining query become a problem


Database replication 
- making copies of the databases
- problems can be inconsistency between databases
- Replications - need some way replicate them
	- More read or write?
	- single-primary Replication / master-salve 
		- read and write to primary, read only to the secondary servers
		- primary will updates the secondary
		- problem - timming, replication is not update fast enough, so user can not read the correct data, like a blog site, where there is nore read request than write
		- Good for many read request
		- if a lo of write request, then it will be a single point of failure

	- Multi-primary replication 
		- multiple primary server, distribute the wirte request to database
		- trade off, replication, need to replicate with other servers
		- if two users edit same data but different database, this can cause problem 
		- need rules to systematically to deal with this
			- depend on time stamp
			- need to define the mechanism to resolve these conflicts


Caching 
	- client side caching  
		- broswers save the files
		- in the header tag, setup cache 
			- cache control: max-age=86400
		- Etag - entity tag, client send etag along to make http request, if Etag is the same as the one in the server, server send back 304 code mean no reload
		- cache control 
			- public caching - anyone can see this
			- private caching - need authentication 
	- Server side caching 
		- have the webserver talk to cache first befor reading from the database
		- cache invalidation - when cached data is no longer valid
			- set timer / expiration date
			- mechanism to check or validate
			- 


Benchamrking
	-ApachBench - test load of the server















































