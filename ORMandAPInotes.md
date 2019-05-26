## ORM 


***Python Review***
***Object-Oriented Programming***

~~~
class Flight:
	
	def __init__(self, origin, destination, duration):
		self.origin = origin
		self.destination = destination
		self.duration = duration

~~~


- If running current file, run the main function
- Useful when importing to another file as module, so that the main() won't run.
~~~
if __name__ == "__main__":
	main()
~~~


***ORM***
- Object relationals mapping
- Using OOP to interact with database


Model 
- For every tables inside a database, there is one class define inside the model file.


If current file is running, then run this. app.app_contexrt tell the program how to interact with the app, thru command line or web request. 
~~~
if __name__ == "__main__":
	with app.app_context():
		main()

~~~


Flask SQLAlchemy, using object to query database
Constructed own class to interact with the databases


***Relationship***
Relationship between table in model class




***API***

- Often uses URL 


- different request method or HTTP method
	- get - request.get(url) - retrieve information 
	- post - request.get(url) - create information 
	- put - request.get(url) - replace information
	- patch - request.get(url) - update information
	- delete - request.get(url) - delete information


- Status codes
	- 200 OK 
	- 201 Created
	- 400 Bad Request
	- 403 Forbidden
	- 404 Not Found 
	- 405 Method Not Allowed
	- 422 Unprocessible Entity 

- API Key
	- limit API calls
	- identify who make the call 
	


 

















