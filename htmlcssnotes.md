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
<html>       // begin html content or the contents of the websites

</html>		 // end of html content
~~~

### Head contents

***Head Tag***
- Metadata or information about the pages, reference links or files
- information that helpful to the browser
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
	- margin - outside spacing of the div in this case
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


***Styling table***
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




## HTML Part II

Anchor Tag
~~~
<a href="filename or link"> Click me </a>
~~~


***Link to different places/content in the same pages by id attributes***
~~~
<h2> Table of contents</h2>
<ul>
	<li><a href="#section1">Section 1</a>></li>>
	<li><a href="#section2">Section 2</a>></li>>
	<li><a href="#section3">Section 3</a>></li>>
</ul>>

<h2 id="section1">Section 1</h2>>
<p>babkdasjf fdsaljfdsf dsa fpods fapos fdsaf aoidsf adf</p>>

<h2 id="section2">Section 2</h2>>
<p>babkdasjf fdsaljfdsf dsa fpods fapos fdsaf aoidsf adf</p>>

<h2 id="section3">Section 3</h2>>
<p>babkdasjf fdsaljfdsf dsa fpods fapos fdsaf aoidsf adf</p>>
~~~

> Not a good idea to link by class because class refer to a group/collection of items. 
> Great with id because it is uniquely identify a section of the html contents


***HTML4***
- Common organization of the HTML4

~~~
<div class="header">
<div class="nav">
<div class="section">
<div class="footer">

~~~

***HTML5***
- The common organization is built into HTML5 
~~~
<header></header>
<nav></nav>
<section></section>
<footer></footer>
.....
<audio>
<video>
<datalist>
....
~~~

***Different type of the input types***
~~~
<form>
	<div>
		<input type="text" name="name" placeholder="Name">
		<input type="password" name="password" placeholder="Password">
	</div>

	<div>
		Favorite color?
		<input type="radio" name="Red"> Red
		<input type="radio" name="Green"> Green
		<input type="radio" name="Blue"> Blue
	</dir>

</form>
~~~


## CSS Part II

***CSS Selectors***

Nested list/sublist - refer to to the DOM structure
Unorder list inside a order list

***If ul is inside of ol, then color the text to red.***
~~~
ol ul {
	color: red;
}
~~~

Selecting element by HTML attributes
~~~
<input type=text id="button"> 

input[type=text] {
	background-color: red:
}

~~~

***Interacting with users***
~~~
button {
	background-color: red
}

button:hover {
	background-color: orange
}
~~~

***:: before and ::after***
~~~
a::before {
	content: "\21d2 Click here: ";
	font-weight:bold;
}
~~~

***::selection ***

for highlighting feature


***CSS Selectors***

|CSS    |Description                               |
|-------|------------------------------------------|
|a, b   | multiple element selector                |
|a b    | Descendant selector                      | 
|a > b  | child selector, select immediate child   |
|a + b  | Adjacent Sibling selector                |
|[a=b]  | Attribute Selector                       |
|a:b    | Pseudocclass Selector                    |
|a::b   | Pseudoelement Selector                   |


> Use sublist for examples





## Responsive Design 

- Making web pages adapt to change in screen size and different devices 

***Responsive Design Strategies***
- Media query 
- Viewport 
- Flexbox
- Grids


***Medeia Query***

- @media mean create media query and apply the css in particular situation 
- in this case the media is print. The 3rd paragraph will not appear when printing the HTML file 

~~~
<head>
	<title>My web pages!</title>
	<style>
		@media print {
			.screen-only {
				display:none;
			}
		}

	</style>
</head>

<body>
	<p>This is a paragraph</p>
	<p>This another paragraph</p>
	<p class="screen-only">This paragraph won't appear when you print </p>
</body>

~~~


***Media as Screen size*** 

~~~
<style>
	@media (min-width: 500px){
		h1::before{
			content:"Welcome to my pages!";
		}
		background-color:red;
	}

	@media (max-width: 499px){
		h1::before  {
			content: "Welcome!";
		}
		background-color:blue;
	}

</style>
~~~


***Flexbox***

- built in CSS
~~~

<head>
	<style>
		.container {
			display: flex;                      <-- flexbox features
			flex-wrap: wrap;					<-- wrap around features, wrap around next line
		}

		.container > div {
			background-color: springgreen;
			font-size: 20px;
			margin: 20px;
			padding: 20px;
			width: 200px; 
		}

	</style>

</head>

<body>

	<div class="container">
		<div>A. fasdifa fadsf ads f wr gre g reh  fadsf</div>
		<div>B. fa sdf rg qr g re g q3r g  edf a sdf as dg f</div>
		<div>C. fkdfaf we f ewarg roeg   u ou ou oiuoiu oi o</div>
		<div>D. daoh fw AFOUEWA OFEWF UOWE UFWUEFUWE OFUAWOF</div>
		<div>E. k faduf oauf oewaufo waeofuowaeufoaweufoaw faowe</div>
	</div>

</body>


~~~~


***Grid***

~~~
<head>
	<style type="text/css">
		.grid {
			background-color: green;
			display: grid;                          <---- grid format
			padding: 20px;
			grid-column-gap: 20px;					<--- use with grid display 	
			grid-row-gap: 20px;
			grid-template-columns: 200px 200px auto;    <---- auto mean auto resizing

		}

		.grid-item {
			background-color: white;
			font-size: 20px;
			padding: 20px; 
			text-align: center;
		}
	</style>
</head>

<body>
	<div class="grid">
		<div class="grid-item">1</div>
		<div class="grid-item">2</div>
		<div class="grid-item">3</div>
		<div class="grid-item">4</div>
		<div class="grid-item">5</div>
		<div class="grid-item">6</div>
		<div class="grid-item">7</div>
		<div class="grid-item">8</div>
		<div class="grid-item">9</div>
		<div class="grid-item">10</div>
		<div class="grid-item">11</div>
		<div class="grid-item">12</div>
	</div>
	
</body>

~~~



### Boostrap
CSS Library
Many different classes for styling the HTML code

~~~
<head>
	<title>My website</title>
	<link rel="stylesheet" type="text/css" href="www.bostraplink......com">
</head>

<body>
	<div class="container">
		<h1>Hello, world!</h1>
		<p>dasf g rw gf ae rf a ewr fa rew gi hiih iuhiu hih khkj kj k jb kk </p>
	</div>
</body>
~~~

- Boostrap styling column 

class="col-lg-3 col-sm-6"

large screen take 3 out of the 12 div boxes, small screen use 6 out of the 12 div boxes



### SASS

Extension of CSS with programatics ability 
Need to install SASS 
Alternatives: LESS

> All variable in SASS begin with a $ sign
> SASS file has file extension .scss
> Need to convert .scss to .css with the sass command
>    sass variables.scss variables.css

variables.scss file 
~~~
$color: red;

ul {
	font-size: 14px;
	color: $color;
} 

ol {
	font-size: 18px;
	color: $color;
}
~~~

> sass --watch variable.scss:variable.css
> In the above command, every time a change in .scss file will automatically compile to .css file


***Nested SASS***

~~~
div {
	font-sizeL 20px;

	p {
		color: blue;
	}

	ul {
		color: green;
	}
}
~~~


***SASS inheritance***

~~~
%message {
	font-size: 20px;
	font-family: somefontfamily;
	font-weight: bold;
	padding: 10px;
	margin: 20px; 
}

.success {
	@extend %message;
	background-color: green;
}

.warning {
	@extend %message;
	background-color: orange; 
}

.error {
	@extend %message;
	background-color: red; 
}
~~~

























