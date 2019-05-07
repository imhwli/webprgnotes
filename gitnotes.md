## Version Control - Git

- Keep track of changes to code
	- history of changes
	- versioning changes

- Synchronizess code between different people
	- colloboration

- Test changes to code without losing the original 
	- branching

- Revert back to old version of code. 
	- revert back to previous commits or chnages



## GitHub 

### Part I

***Clone a repository***
~~~
git clone <url>
~~~

***What files to keep track/commit
Add files to stage area for keeping track***
~~~
git add <filename>
~~~

***Take a snapshop of the repository***
***Add comment about the snapshot***
~~~
git commit -m "message"
~~~

***Combining add and commit***
~~~
git commit -am "message message"
~~~

***Check status of the repository***
~~~
git status
~~~

***Push changes to remote git server***
~~~
git push 
~~~

***Get changes from remote server***
***If changes are made in the codes/files***
~~~
git pull 
~~~

***Merge Conflicts 
It happens when two people change same lines in the file
Git don't know which one to pick 
User needs to manaually go into the code and fix that***

~~~
a = 1 
<<<<< HEAD         
b = 2								<--- your changes
=====
b = 0							 	<--- remote server changes
>>>>> 7938749821375913847293847
c = 3
d = 4
e = 5
~~~


***show history of changes, like changes, who changes***
~~~
git log
~~~

***revert code back to previous version***
~~~
git reset --hard <commit hash>        <-- revert back to specific commit 
git reset --hard origin/master		  <-- revert back to master branch
~~~

***Refererence of all commits***
~~~
git relog
~~~


### Part II

***Branching***
Branching in multiple directions 
Tagging each direction 

***Merging***
Merging sub branches to the master

>HEAD is pointing to current working branch. 

Merge Conflicts
- smiliar to 


~~~
git branch 								<-- list out all the branches and current working branches

git branch feature						<-- create new branch 

git checkout feature					<-- switch working branch
git branch
	
git log
 
~~~


***Pushing branches to remote server***
~~~
// assume only master branch, create new branch
git branch feature

// assume added or made some changes to feature branch. 
// now try to push the branch to remote server, github
git push --set-upstream origin feature

~~~


Branching
~~~
git branch
git checkout
git merge
~~~


***Remote*** 
- version of the repository store in somewhere else like your computer
- "origin" refer to remote repository in github, in github case


~~~
git fetch							<-- get/download updates from remote repository 
git merge origin/master				<-- Point HEAD to origin/master 

// OR combinine both commands 

git pull 

~~~


***Fork***
- a copy or seperate version of the repository 
- allow user to make changes, similar to branching
- Pull request, review changes on forked branches and collaboration
- when ready, reviewed and tested, can merge to the master repository















