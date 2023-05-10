
# CD/CI Application

## Description

* We have written a basic REST API using the [Flask](http://flask.pocoo.org) microframework
* Basic database operations and migrations using the Flask wrappers around [Alembic](https://bitbucket.org/zzzeek/alembic) and [SQLAlchemy](https://www.sqlalchemy.org)
* Written automated unit tests with [unittest](https://docs.python.org/2/library/unittest.html)

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
$ docker build -t ci-cd-app:latest .
$ docker run -d -p 8000:8000 ci-cd-tutorial-sample-app:latest
```
