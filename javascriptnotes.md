## JavaScript

- Running code on the client side

Different javascript standard out there. Some browser support different standard
ES6 - JavaScript standard, most browser support this


~~~
<!DOCTYPE html>
<html>
	<head>
		<script type="text/javascript">
			alert('Hello!');
		</script>
		<title>My website</title>
	</head>	
	<body>
		<h1>Welcome!</h1>
	</body>
</html>

~~~

Button to trigger the javascript
~~~
<!DOCTYPE html>
<html>
	<head>
		<script type="text/javascript">
			function hello() {
				alert('Hello!');
			}
		</script>
		<title>My website</title>
	</head>	
	<body>
		<h1>Welcome!</h1>
		<button onclick="hello()">Click Here!</button>
	</body>
</html>

~~~


Events to trigger whick block of javascript to run
- onclick
- onmouseover
- onkeydown
- onkeyup
- onload
- onblur



***Modifying the DOM***
~~~
<!DOCTYPE html>
<html>
	<head>
		<script type="text/javascript">
			function hello() {
				document.querySelector('h1').innerHTML = "Goodbye!";
			}
				# querySelector only will select the first match		

		</script>
		<title>My website</title>
	</head>	
	<body>
		<h1>Welcome!</h1>
		<button onclick="hello()">Click Here!</button>
	</body>
</html>
~~~

Document.getElementByid()
vs
CSS selector
vs
QuerySelector selector

document.querySelector("tag")
document.querySelector("#id")
document.querySelector(".class")




Handling event 
~~~
<!DOCTYPE html>
<html>
	<head>
		<script type="text/javascript">

			document.addEventListener('DOMCounterLoaded', function() {
				document.querySelector('buton').onclick = count;

			});

			function hello() {
				document.querySelector('h1').innerHTML = "Goodbye!";
			}
				# querySelector only will select the first match		

		</script>
		<title>My website</title>
	</head>	
	<body>
		<h1>Welcome!</h1>
		<button onclick="hello()">Click Here!</button>
	</body>
</html>
~~~


> addEventListener - Add event, two parameters
> DOMCounterLoaded - When DOM is loaded event
> 
> Higher order function - treat function as value, like passing function as variable


> Function() vs ()=>
> Use function() with this keyword
>



***Variable***
- const
- let - exist in the most inner scope of the curly braces
- var - exist within the function even with curly braces




***Event handler, conditions*** 
- to trigger event


***local storage***
- localStorage.getItem()
- localStorage.setItem()


***Ajax***
- Stand for asychronize javascript and XML
- technique to send and retrive data in the background without reloading the webpage
- request data more information from web server without reload the whole page



***Web Socket.IO***

- Full Deplex communication - server and client talk to each other
- client send data to server, server broadcast it out to all listening client








































