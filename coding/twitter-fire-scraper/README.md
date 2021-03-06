# What is this?

This is a Python Twitter "Fire event" scraper/listener.

It is an application that will listen for or scrape data relating to house fires 
(Chicago specifically) in order to analyze how people use Twitter as a platform
to report and talk about disasters.

# How will this use Twitter data?

This application is to help the American Red Cross analyze data about house fires
for an Illinois Institute of Technology Interprofessional Project class.

This data collected will not be sold or marketed at all and is only going to be
used to understand house fires in Chicago.

# How do I run this?

## Setting up your secrets

A note: These are called 'secrets' for a reason. Don't ever stage or commit
`secrets.json`, please.

### Twitter secrets

You will need:

- A twitter developer account & API key
    - A consumer key
    - A consumer secret
    - An access token
    - An access secret

- A twitter handle you're authorized to make queries on behalf of

You are to put these into a file called `secrets.json` at the root of this
directory.

An example file is provided for you to base your file off of, called
`secrets.example.json`.

### MongoDB secrets

There is an entry in `secrets.json` that expects a MongoDB connection string,
and a default one is provided in `secrets.example.json`.

It expects a URL to a MongoDB server, and looks like this:

    mongodb://localhost:27017/

## Setting up a database

For the database, we have chosen to use MongoDB since twitter data is stored in
JSON and MongoDB is very well-suited for storing JSON data.

Follow [this tutorial](https://docs.mongodb.com/v3.2/tutorial/) on how to install MongoDB.

## Installing Python

This runs Python 2.7, so [install Python 2.7](https://www.python.org/downloads/release/python-2713/)

I used Pipenv, a Python dependency manager, to track and manage the packages
installed.

This is so everyone else can reproduce the Python environment I have on my
laptop/desktop.

### Setting up Pipenv

You can install Pipenv by executing 
    
    python -m pip install pipenv

You can then install all packages in this folder's `./Pipenv` by executing

    python -m pipenv install --two
    
Then, you can run the app by executing

    python -m pipenv run python app.py
    
or run tests by executing

    python -m pipenv run python tests/<TESTNAME>.py

#### Troubleshooting Python2/3 issues

This section only really applies if you have both Python 2 and 3 installed.

Make sure that `python` refers to Python 2.7! If it doesn't, try going to
Python 2.7's installation directory and installing it via opening a shell there.

`where python` and `which python` can help you figure out the location of your
Python executables.

If you get odd errors and have both Python 2 and 3 (as I do), try appending
`--two` to the `pipenv` command to tell it to use Python 2.

If that doesn't work (or if `python` refers to Python 3), then executing `python2 -m
pipenv install myCoolPackage` has a greater chance of working, assuming
`python2` refers to a Python 2.7 executable.

For reference, I run my files by executing `python2 -m pipenv run python <FILE>.py`.

The nuclear option (uninstall Python 3 entirely) will definitely fix all these
problems.

# Running the app

You can run the app by executing `python -m pipenv run python app.py`.

Currently, ***the app is blank***. This will change as soon as the frontend is built and
a fully-functional backend is built.

## Running a functional demo

Inside this folder, there are two files called `Run-Demo.bat` and
`Run-Demo.ps1`. You can run either of those to start

# Running tests

You can execute `python -m pipenv run python tests/<TESTNAME>.py` to run a test.

To run all tests, execute `python -m pipenv run python tests/test/__init__.py`
and all tests will run.

# What was this adapted from?

A movie sentiment analysis project by [Raul](https://github.com/raaraa/), the
repository [is here](https://github.com/raaraa/movie-twitter-sentiment) and a
live site [is here](https://movie-tweet-sentiment.herokuapp.com/).

Commit `2fb844e8c081c1dc31cfb4760e3a80cefb6a0eee` was used.

# Why Python 2?
[Raul's](https://github.com/raaraa/) project was in Python 2, and adapting it
to Python 3 wasn't worth the time.

We could concievably adapt all the code to Python 3, but there's no good
reason to yet.

# There's got to be a better way to run this than from the command line!

There is! Use an IDE (like PyCharm, which I use) that preferably integrates with 
Python to show you import errors, syntax errors, etc. Go google "Python IDE" and
pick one you like.