# python_django_sample

## see django version

Mac/Linux

python -m django --version

Windows

py -m django --version

## Creating a project

django-admin startproject mysite

This will create a mysite directory in your current directory.


Let’s look at what startproject created:

mysite/
    manage.py
    mysite/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py


These files are:

* The outer mysite/ root directory is a container for your project. Its name doesn’t matter to Django; you can rename it to anything you like.
* manage.py: A command-line utility that lets you interact with this Django project in various ways. You can read all the details about manage.py in django-admin and manage.py.
* The inner mysite/ directory is the actual Python package for your project. Its name is the Python package name you’ll need to use to import anything inside it (e.g. mysite.urls).
* mysite/__init__.py: An empty file that tells Python that this directory should be considered a Python package. If you’re a Python beginner, read more about packages in the official Python docs.
* mysite/settings.py: Settings/configuration for this Django project. Django settings will tell you all about how settings work.
* mysite/urls.py: The URL declarations for this Django project; a “table of contents” of your Django-powered site. You can read more about URLs in URL dispatcher.
* mysite/asgi.py: An entry-point for ASGI-compatible web servers to serve your project. See How to deploy with ASGI for more details.
* mysite/wsgi.py: An entry-point for WSGI-compatible web servers to serve your project. See How to deploy with WSGI for more details.

## The development server

Let’s verify your Django project works. Change into the outer mysite directory, if you haven’t already, and run the following commands:

...\> py manage.py runserver


Now that the server’s running, visit http://127.0.0.1:8000/ with your Web browser. You’ll see a “Congratulations!” page, with a rocket taking off. It worked!

http://127.0.0.1:8000/hello/

## Changing the port

By default, the runserver command starts the development server on the internal IP at port 8000.

If you want to change the server’s port, pass it as a command-line argument. For instance, this command starts the server on port 8080:

Windows

...\> py manage.py runserver 8080

Mac/Linux

$ python manage.py runserver 8080

If you want to change the server’s IP, pass it along with the port. For example, to listen on all available public IPs (which is useful if you are running Vagrant or want to show off your work on other computers on the network), use:

Windows

...\> py manage.py runserver 0:8000

Mac/Linux

$ python manage.py runserver 0:8000

0 is a shortcut for 0.0.0.0. Full docs for the development server can be found in the runserver reference.

### Automatic reloading of runserver

The development server automatically reloads Python code for each request as needed. You don’t need to restart the server for code changes to take effect. However, some actions like adding files don’t trigger a restart, so you’ll have to restart the server in these cases.



