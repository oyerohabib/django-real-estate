# Real Estate Django Web App

A real estate listings website built with `python` `django` `bootstrap`.

A simple, reponsive  website. Built with:

- Python 🐍
- Django 🎸
- Bootstrap 4 🌈
- Vanilla JS - ES6
- JQuery

If you are new to Django, checkout the [Django 2.x Cheat Sheet](https://github.com/oyerohabib/django-real-estate/blob/master/django_cheat_sheet.md)

If you want to deploy this Web App In Ubuntu 18.04 Server, Please Follow this [Guide](https://github.com/oyerohabib/django-real-estate/blob/master/Django_Deployment_to_Ubuntu_18.04.md) 

## How to run this project (Ubuntu 18.04)

1. **Clone the project**

```sh
git clone https://github.com/oyerohabib/django-real-estate.git
```

2.  **Make sure you are in *django-real-estate* folder**

   1. Install all dependencies

      ```sh
      pip install -r requirements.txt
      ```

3. **Install PostgreSQL in your Ubuntu 18.04**

   1. Enable PostgreSQL Apt Repository

      ```sh
      sudo apt-get install wget ca-certificates
      
      wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
      
      # Now add the repository to your system.
      
      sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" >> /etc/apt/sources.list.d/pgdg.list'
      ```

   2. Install PostgreSQL on Ubuntu

      ```sh
      sudo apt-get update
      sudo apt-get install postgresql postgresql-contrib
      ```

   3. Connect to PostgreSQL

      ```sh
      sudo su - postgres
      psql
      ```

      Now you are logged in to PostgreSQL database server. To check login info use following command from the database command prompt.

      ```sh
      postgres-# \conninfo
      ```

   4. Create a database

      ```sh
      CREATE DATABASE real_estate;
      ```

   5. Create user 

      ```sh
      CREATE USER pks WITH PASSWORD 'abc123!';
      ```
   
4. **Run Migrations**

```sh
python manage.py makemigrations
python manage.py migrate
```

5. **Run Server**

```sh
python manage.py runserver 
```

And you are good to go. 


**To run with SQLite only**

Go inside the 'realestate' folder and open 'settings.py' file and replace

```sh
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'real_estate' ,
        'USER': 'pks',
        'PASSWORD': 'abc123!',
        'HOST':'localhost',
        
    }
}
```

To: 

```sh
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}

```

This is the default configuration of Django database.