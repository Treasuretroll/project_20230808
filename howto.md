# Correct way to create a Django Project

There are dozens of ways, which developers use to start their Django projects. Possibly, none of them would be a wrong way, but in this post we will be telling you a way which is very helpful and suitable not only in development but also in production (deployment). Not only this, in this post we will teach you how to integrate Git/Github with your project from the very beginning.

# Creating the Project Directory

So, let’s get to the work. First of all, choose a location on machine, where to save projects and cd to that directory. Then create a new directory and cd into that:

$ mkdir dev 
$ cd dev

Now, this dev folder will host all of your individual projects. Inside this dev folder create a new directory (with the name of your project/app) and cd into that. This directory will be referred to as your project directory:

$ mkdir newproject && cd newproject

# Creating and activating the Virtual Environment

Install virtual environment and activate it.

MACOS/Linux 
$ python3 -m venv .

Activate on MACOS/Linux
$ source bin/activate

# Activate on Windows
.\Scripts\activate

Create a new directory with name ‘src’

$ mkdir src && cd src


Correct way to create a Django Project

There are dozens of ways, which developers use to start their Django projects. Possibly, none of them would be a wrong way, but in this post we will be telling you a way which is very helpful and suitable not only in development but also in production (deployment). Not only this, in this post we will teach you how to integrate Git/Github with your project from the very beginning.
Creating the Project Directory

So, let’s get to the work. First of all, I will suggest you to choose a location on your machine (Windows/ Mac), where you want to save most of your projects and cd to that directory. Then create a new directory and cd into that:

$ mkdir dev
$ cd dev

Now, this dev folder will host all of your individual projects. Inside this dev folder create a new directory (with the name of your project/app) and cd into that. This directory will be referred to as your project directory:-

$ mkdir newproject && cd newproject

Creating and activating the Virtual Environment

Install virtual environment and activate it.

$ virtualenv -p python3 .
# or
$ virtualenv .

# Activate on MACOS/Linux
$ source bin/activate

# Activate on Windows
.\Scripts\activate

Create a new directory with name ‘src’

$ mkdir src && cd src

Installing Django and starting the project

Use pip to install django

$ pip install django

Now inside the src directory create the project

$ django-admin.py startproject newproject .

You must note the following two things.

    We have started a project with name ‘newproject’ and same is the name of the project directory (and also the virtualenv).
    There is a trailing . (dot).

Creating local Git repository

Browse to the project folder (i.e. newproject) and run the following command. This will initialize an empty Git repository.

$ git init

Now create a file called .gitignore in the project directory. The function of this file is that, it will not add the folders\files mentioned (pattern) in it to the git repository. This is used for not adding venv, env, temp, db files to the repository.