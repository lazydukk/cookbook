# Cloning/Setting up a Django Project

#### 1. Cloning the repo
* Using the *github cli* CLI or downloading the repo or any other method

#### 2. [Creating a Virtual environment](/ven) 

#### 3. Installing requirements
* running `pip install -r requirements.txt`

#### 4. Creating a PostgresSQL DB
(you can use preferred SQL DB)
(pgAdmin & POstgres must be installed)

* run these command on your terminal
```shell
$ psql postgres
$ CREATE DATABASE databasename
$ \connect databasename
```

* log into pgAdmin & then check if the DB exist

* add the secrets into `.env` then import them the to the `settings.py`
example:
```python
*settings.py*
DATABASES = {‘default’: {‘ENGINE’: ‘django.db.backends.postgresql_psycopg2’,
‘NAME’: env(‘DATABASE_NAME’),
‘USER’: env(‘DATABASE_USER’),
‘PASSWORD’: env(‘DATABASE_PASS’),}}
```
#### 5. Genreate a SECRET_KEY
* using [djecrety](https://djecrety.ir/) you can generate a *secret_key*
* to migrate:
```shell
$ python manage.py makemigrations
$ python manage.py migrate
```

#### 6. Creating a new superuser
```shell
python manage.py createsuperuser
```
#### 7. Running the server
```shell
python manage.py runserver
```

credits/source: [alicecampkin](https://alicecampkin.medium.com/setting-up-a-forked-django-project-53d5939b7e9e)