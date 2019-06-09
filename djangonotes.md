## Django 


***Project components***
- __init__.py - this folder is python packages, a group of different python files group together for some purpose
- manage.py - scripts for perform useful task/operations
- setting.py - setting for the application, like timezone, what apps installed, database type 
- urls.py - url route that users can go to 
- wsgi.py - use for hosting in the web server
- project_name/ - where everything is stored 


For starting a new django project
~~~
django-admin startproject projectname
~~~

> A Django project create all the componet for a web site
> A Django project contains multiple apps
> Where each one of those app serve a single purpose

For starting a new app 
~~~
python managy.py startapp hello 
~~~


Model - define what type of data that can store 


Create/updatin the databse tables
~~~
python manage.py makemigrations
python manage.py makemigrate
~~~


Generate the SQL query to
~~~
python manage.py sqlmigrate <appname> <id#>
~~~


Entering Django shell 
~~~
python manage.py shell
~~~

Create super user for admin page
~~~
python manage.py createsuperuser
~~~


Adding route

Linking route




Customize the Django admin page



























