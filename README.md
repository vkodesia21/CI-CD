[![Build Status](https://travis-ci.org/edonosotti/ci-cd-tutorial-sample-app.svg?branch=master)](https://travis-ci.org/edonosotti/ci-cd-tutorial-sample-app)
[![codebeat badge](https://codebeat.co/badges/0e006c74-a2f9-4f34-9cf4-2378fb7d995a)](https://codebeat.co/projects/github-com-edonosotti-ci-cd-tutorial-sample-app-master)
[![Maintainability](https://api.codeclimate.com/v1/badges/e14a2647843de209fd5e/maintainability)](https://codeclimate.com/github/edonosotti/ci-cd-tutorial-sample-app/maintainability)

# CD/CI Application

## Description

This sample Python REST API application was written for a tutorial on implementing Continuous Integration and Delivery pipelines.

It demonstrates how to:

* Write a basic REST API using the [Flask](http://flask.pocoo.org) microframework
* Basic database operations and migrations using the Flask wrappers around [Alembic](https://bitbucket.org/zzzeek/alembic) and [SQLAlchemy](https://www.sqlalchemy.org)
* Write automated unit tests with [unittest](https://docs.python.org/2/library/unittest.html)

## Requirements

* `Python 3.8`
* `Pip`
* `virtualenv`, or `conda`, or `miniconda`



## Installation

Initalize and seed the database:

```sh
$ python -m unittest discover
$ flask db upgrade
$ python seed.py
```

## Running tests

Run:

```sh
$ python -m unittest discover
```

## Running the application

### Running locally

Run the application using the built-in Flask server:

```sh
$ flask run
```

### Running on a production server

Run the application using `gunicorn`:

```sh
$ pip install -r requirements-server.txt
$ gunicorn app:app
```

To set the listening address and port, run:

```
$ gunicorn app:app -b 0.0.0.0:8000
```

## Running on Docker

Run:

```
$ docker build -t ci-cd-tutorial-sample-app:latest .
$ docker run -d -p 8000:8000 ci-cd-tutorial-sample-app:latest
```

## Deploying to Heroku

Run:

```sh
$ heroku create
$ git push heroku master
$ heroku run flask db upgrade
$ heroku run python seed.py
$ heroku open
```
