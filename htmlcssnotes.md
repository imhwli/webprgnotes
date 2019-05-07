## HTML notes

HTML Examples
~~~
<!DOCTYPE html>                     
<html> 							   
	<head>							
		<title>My Web Page!</title>
	</head>
		
	<body>
		<h1> This is the largest headline. </h1>
		<h2> This is also a large headline. </h2>
		<h3> This is a slightly smaller headline. </3>
		<h4> This is even smaller headline. </h4>
		<h5> This is the second smallest headline. </h5>
		<h6> This is the smallest headline. </h6>
	</body>
</html>							
~~~

***DOC type***
- tell the browser what type of file it is, like html5 or something else. 



***HTML content tag***
~~~
<html>       // begin html content 

</html>		 // end of html content
~~~

### Head contents

***Head Tag***
- Metadata or information about the pages, reference links or files
~~~
<head>

</head>
~~~

***Title tag***
- title of the webpage
~~~
<title>

</title>
~~~




### Body contents

***Body Tag - the content of the page***
~~~
<body>
	
</body>
~~~


***HTML has 6 build-in heading tags***
~~~
<h1> This is the largest headline. </h1>
<h2> This is also a large headline. </h2>
<h3> This is a slightly smaller headline. </3>
<h4> This is even smaller headline. </h4>
<h5> This is the second smallest headline. </h5>
<h6> This is the smallest headline. </h6>
~~~


***Unorder list - bullet point***
~~~
<ul>
	<li>one item</li>
	<li>another item</li>
	<li>another one</li>

</ul>
~~~

***Order list - automatically numbered***
~~~
<ol>
	<li>first item</li>
	<li>second item</li>
	<li> another item </li>
	<li>third item</li>
</ol>
~~~

Images tag - no closing tag, self closing tag
- html attributes, src, height, width
~~~
<img src="cat.jpg" height="200" width="200">
~~~
50% of length base of the broswer, self adjusting
~~~
<img src="cat.jpg" height="50%" width="50%">
~~~

Table Tag
- tr -> table row
- td -> table data
~~~
<table>
	<tr>
		<td>First Name</td>
		<td>Last Name</td>
		<td>Duration</td>
	</tr>
	<tr>
		<td>person fname</td>
		<td>person lname</td>
		<td>Years</td>
	</tr>
</table>
~~~


Form tag - get inputs
~~~
<form>
	<input type="text" placeholder="Full Name" name="name">

	<button>Submit </button>
</form>
~~~



DOM - document Object Model

HTML 
 	- Head
 		- Title
 			- "Page title"
 	- Body 
 		- "Hello, word!"
 		- table 
 		- form



### CSS - styling

p - paragraph tag
style - html attributes for styling html
color can use word or hex color value
~~~
<h1 style="color:blue;text-align:center;"> Welcome to My WebPage! </h1>

<p>Hello, world! this is a paragraph of text.</p>
<p>This is another paragraph </p>
~~~


##### Adding style tag in head tag 
- put the styling css inside head tag 
- the whole files use that css styling

~~~
<head>
	<title> My title </title>
	<style>
		h1 {
			color: blue;
			text-align: center;
		}
	</style>
</head>
~~~


Problem with this is that when another HTML file need that style code, will need to copy and paste the the styling code to another html page. And to make chanege to every h1 tag style means change every HTMl files


##### Seperate html and css file

~~~
<head>
	<title> My title </title>
	<link ref="stylesheet" href="style.css">
</head>
~~~

CSS file 
~~~
h1 {
	color: blue;
	text-align: center;
}

p {
	color: red;
}
~~~

> div tag sectioning HTML code. Dividing HTML into sections


#### CSS properties

- controlling spacing 
	- margin - ourside spacing of the div in this case
	- padding - inside spacing of the div in this case

~~~
div {
	background-color: teal;
	width: 100px; 
	height: 400px; 
	margin: 30px;
	padding; 20px;
}

~~~

- Font properties
	- font-family: can specify multiply font family, pick the first that work for the browser
	- font-size 
	- font-weight

~~~

div {
	font-family: Ariel, san-serif; 
	front-size: 28px;
	font-weight: bold;
}

~~~


Border on dicv tag.
specify border line around the div
solid line, dotted line

~~~
div { 
	border: 3px, solid blue
}

~~~


Styling table
~~~
table {
	vorder: 2px solid black;
	border-collapse;          <-- remove double border
}

th {
	border: 1px solid black;
}

td {
	border: 1px solid black; 
}


*OR put them in one bracket

th, td {
	border: 1px solid black;
	text-align: center;
}
~~~


***span tag***   
- similar to div tag, for organizing and sectioning html 

- difference between span and div 
	- span is in-line and usually used for small chunk of html inside a line 
	- div is block-line, grouping larger chunk of html code


***id vs class***
- id must be unique, only one element in the html can have that id 
- class can group html elements, 
- id uses # and class uses . in css syntase
- use id and class to identify section of the html 
- id refers to one particular element in html 
- class refers multiple elements in html


CSS file
~~~
#top {
	font-size: 36px; 
}

#middle {
	font-size: 24px; 
}

#bottom {
	font-size: 12px; 
}

.name {
	font-weight: bold;

}
~~~

HTML file
~~~

<idv id="top">
	This is the <span class="name"> top </span> of the message
</div>

<idv id="middle">
	This is the <span class="name"> middle </span> of the message
</div>

<idv id="bottom">
	This is the <span class="name"> bottom </span> of the message
</div>

~~~


> HTML tag render the closest css properties to itself according to the DOM.




## Part II



