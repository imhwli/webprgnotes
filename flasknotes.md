# Flask

## Python Review

f stands for format, meaning format string. Python 3.6 or higher.
~~~
name = input()
print(f"hello, {name}!")
~~~

- variable, interpreted
- condition, if/elif/else
- indentation is important
- string
- tuple
- list, order sequence of data
- Good idea/design to have same data type in the element in the list
- set, no order, no duplicate/repeat value, useful to decide if data is in the set or not
- dictionary, key to value, mapping one value to another, 
 
- function
Old way to format string, older than 3.5
print("{} square is {}".format(i, square(i)))
 
- importing python modules, make sure __name__ is setup, use main function


Interpretation: If running current file, run the main fucntion. 

\_\_name\_\_ refer to current file

~~~
if __name__ == "__main__":
	main()
~~~

- classes and constructor



***HTTP***
- HTTP request 
- Server get request and figure what to do and response back



## Flask

~~~
from flask import Flask

app = Flask(__name__)         				<-- create new Flask app with current file
											<--  __name__ refer to current file
@app.route("/")
def index():
	return "Hello, world!"


~~~


- decorader 

- environment variable, set flask where to look for the python file to run 
- export FLASK_APP=apllcaition.py     <--- set flask environment variable


~~~
@app.route("<string:name>")
def hello(name):
	name = name.capitalize()
	return f"Hello, {name}."

	return f"<h1>Hello, {name}.</h1>"

~~~



***Template***

Displaying HTML file
Flask will look immediately the HTML file in the template directory in the current directory 

>
> app.py 
> template
>	 index.html
>

~~~
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
	return render_template("index.html")


~~~

HTML file
~~~
<!DOCTYPE html>

<html>
	<head>
		<title>A website</title>
	</head>

	<body>
		<h1>Hello, world!</h1>
		<h1>{{ headline }}</h1>        			<-- Using variables
	</body>
</html>

~~~


***Using variable in template***

jinja2 templating lanaguage, that flask use for its templating. 

~~~
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
	headline = "Hello, world!"
	return render_template("index.html", headline=headline)

~~~


Set flask to debug mode to auto reload when change the file. 



***Program to tell whether if today is new year or not.***

~~~
import datetime

from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
	now = datetime.datetime.now()
	new_year = now.month == 1 and now.day == 1
	return render_template("index.html", new_year=new_year)

~~~


- jinja2 conditional statement, similar to python
- Users will not see the conditionals statement, template got process in the server and then send to user, so users will not see the complexity 
- jinja2 is installed along with Flask


~~~
<body>
	{% if new year %}
		<h1> Yes! Happy New Year! </h1>
	{% else %}
		<h1>NO</h1>
	{% endif %}
</body>

~~~


***Looping***

application.py
~~~
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
	name = ["Alice", "Bob", "Charlie"]
	return render_template("index.html", names=names)

~~~


template/index.html
~~~
<body>
	<h1>Names</h1>
	{% for name in names %}
		<li> name </li>
	{% endfor %}
</body>

~~~



***Linking pages***

application.py
~~~
from flask import Flask, render_template
 
app = Flask(__name__)

@app.route("/")
def index():
	return render_template("index.html")

@app.route("/more")
def more():
	return render_template("more.html")

~~~

template/index.html
- url_for() is a jinga2 function, it call the more function in the python code

~~~
<body>
	<h1>first page</h1>
	
	<p>dasifhosaidf dsf uaoidsfuoa dsifuoa ifoiwarhjoifahw ofihao fsadifw eiofaiwejf oawe</p>

	<a href="{{ url_for('more') }}">See More</a>
</body>

~~~


template/more.html

~~~
<body>
	<h1>first page</h1>
	
	<p>dasifhosaidf dsf uaoidsfuoa dsifuoa ifoiwarhjoifahw ofihao fsadifw eiofaiwejf oawe</p>

	<a href="{{ url_for('index') }}">Go back</a>
</body>

~~~


***Inheritance***

- template inheritance
- same application.py as the one in Linking pages
- index.html and more.html layout are inherited from layout.html

template/layout.html     <-- parent 
~~~
<html>
	<head>
		<title> This website.</title>
	</head>

	<body>
		<h1>{% block heading %} {% endblock %}</h1>
		
		{% block body %}
		{% endblock %}
	</body>
</html>
~~~


template/index.html   					<-- inherit layout.html format
~~~
{% extend "layout.html"}

{% block heading %}
	First Page 
{% endblock %}

{% block body %}
		
	<p>dasifhosaidf dsf uaoidsfuoa dsifuoa ifoiwarhjoifahw ofihao fsadifw eiofaiwejf oawe</p>

	<a href="{{ url_for('more') }}">See More</a>

{% endblock %}

~~~


template/more.html 						<-- inherit layout.html format
~~~
{% extend "layout.html"}

{% block heading %}
	First Page 
{% endblock %}

{% block body %}
		
	<p>dasifhosaidf dsf uaoidsfuoa dsifuoa ifoiwarhjoifahw ofihao fsadifw eiofaiwejf oawe</p>

	<a href="{{ url_for('index') }}">Go back</a>

{% endblock %}

~~~



***Form***
- users submit data

application.py
~~~
from flask import Flask, render_template, request
 
app = Flask(__name__)

@app.route("/")
def index():
	return render_template("index.html")

@app.route("/hello", methods=["POST"])					<-- support ony POST request
def hello():
	name = request.form.get("name")
	return render_template("hello.html", name=name)

OR

@app.route("/hello", methods=["GET", "POST"])			<-- support both GET and POST requests
def hello():
	if request.method == "GET":
		return "please submit the form instead."
	else:
		name = request.form.get("name")
		return render_template("hello.html", name=name)
~~~

template/index.html
~~~
{% extend "layout.html"}

{% block heading %}
	First Page 
{% endblock %}

{% block body %}
	<form action="{{ url_for('hello') }}" method="post" >
		<input type="text" name="name" placeholder="Enter you name">
		<button>Submit</button>
	</form>
{% endblock %}

~~~

- Can use GET to submit data. When using GET to submit data, it shows up in the url.
- When "name = request.form.get("name")" is call, take the request user made, access the form, and get what part in the form  was called name.


template/hello.html
~~~
{% extend "layout.html"}

{% block heading %}
	 Hello! 
{% endblock %}

{% block body %}
	Hello, {{ name }}!
{% endblock %}

~~~


***Session***

application.py
~~~
from flask import Flask, render_template, request, session
from flask_session import Session     			<-- store data on local server

app = Flask(__name__)

app.config["SESSION_PERMANENT"] = False
app.config["SESSION_TYPE"] = "filesystem"

Session(app)

notes[]

@app.route("/", methods=["GET", "POST"])			
def index():
	if request.method == "POST":
		note = request.form.get("note")
		notes.append(note)

	return render_template("index.html", notes=notes)


	OR and global variable notes list is not needed

	if session.get("notes") is None:
		session["notes"] = []

	if request.method == "POST":
		note = request.form.get("note")
		session["notes"].append(note)

	return render_template("index.html", notes=notes)



~~~

- note is global variable
- notes is kept in the session. unless the flask server is restarted, the notes is persistent


template/index.html 
~~~
{% extend "layout.html"}

{% block heading %}
	 Notes! 
{% endblock %}

{% block body %}
	<ul>
		{% for note in notes %}
			<li> {{ note }}</li>

	</ul>

	<form action="{{ url_for('index') }}" method="post" >
		<input type="text"  name="note" placeholder="Enter note here">
		<button>Add note</button>
	</form>

{% endblock %}

~~~























