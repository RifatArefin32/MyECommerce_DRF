## Project Setup
- Create the project directory
```bash
mkdir MyECommerce
cd MyECommerce
```

- Create a virtual environment to isolate our package dependencies locally and activate it
```bash
python3 -m venv env
source env/bin/activate
```

- Install Django and Django REST framework into the virtual environment 
```bash
pip install django
pip install djangorestframework
```

- et up a new project and check the project by running in local server (localhost:8000)
```bash
django-admin startproject myECommerce
cd myECommerce/
python3 manage.py runserver
```

- Add `'rest_framework'` to our `INSTALLED_APPS` setting.
- If we're intending to use the browsable API we'll probably also want to add REST framework's login and logout views. Add the following to your root urls.py file. Add `path('api-auth/', include('rest_framework.urls'))` to the projects `urls.py` file.

## Setting up PostgreSQL Database
- Add the following items to the `settings.py` of the project directory
```bash
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'myecommerce', 
        'USER': 'myecommerce_user',
        'PASSWORD': 'password',
        'HOST': '127.0.0.1', 
        'PORT': '5432',
    }
}
```
- Install `psycopg2-binary`
```bash
pip install psycopg2-binary
```
- Run migration
```bash
python3 manage.py migrate
```
- Create admin as super user
```bash
python3 manage.py createsuperuser
```