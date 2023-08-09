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

# Create a new directory with name ‘src’

$ mkdir src && cd src

# Installing Django and starting the project

Use pip to install django

$ pip install django

Now inside the src directory create the project

$ django-admin startproject newproject .

You must note the following two things.

    We have started a project with name ‘newproject’ and same is the name of the project directory (and also the virtualenv).
    There is a trailing . (dot).

# Creating local Git repository

Browse to the project folder (i.e. newproject) 
$ cd ../

Run the following command. This will initialize an empty Git repository.

$ git init

Now create a file called .gitignore in the project directory. The function of this file is that, it will not add the folders\files mentioned (pattern) in it to the git repository. This is used for not adding venv, env, temp, db files to the repository.

# Creating a remote Git repository on Github

Open github, log in to your account and create a new repository. Add the name (preferably project name) and description of the repository and create it.

You won’t like to share your important credentials on the github etc. For that we will be using Python Decouple.

$ pip install python-decouple

Create a .env file inside the directory where manage.py file is (i.e. src)

$ nano .env

Open the file and copy the SECRET_KEY from your settings.py

SECRET_KEY=YOUR_SECRET_KEY

Add the following two lines in your settings.py

from decouple import config
SECRET_KEY = config('SECRET_KEY')

Now go to the project directory and check git status to see the files that are untracked

$ git status

You will get something like this

On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

    .gitignore
    bin/
    lib64
    pyvenv.cfg
    src/

Now, add the files and make initial commit using the following codes:

$ git add .
$ git commit -m "Initial Commit"

If you check git status now, it should show the following:

$ git status

On branch master
nothing to commit, working tree clean

Now add the remote origin using this :

git remote add origin https://github.com/YOUR_USER_NAME/newproject.git

It will ask you for the username and password of the github account and then will push it to Github.