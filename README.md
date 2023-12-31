# LIT-test-task
A test task for "Longevity In Time", an API in which a user can register, get an OTP code, get an authorization token, edit their profile and delete it.

### **Stack**
![python version](https://img.shields.io/badge/Python-3.8-green)
![django version](https://img.shields.io/badge/Django-3.2-green)
![sorl-thumbnail version](https://img.shields.io/badge/Django%20REST%20Framework-%203.14.0-green)
![Celery version](https://img.shields.io/badge/Celery-5.3-green)


### Preparing for launch
After copying the repository in your virtual machine.
Install and run Redis:
```
sudo apt-get update
sudo apt-get install redis
sudo service redis-server start
```
Create and activate the virtual environment, update pip:
```
python3 -m venv venv
. venv/bin/activate or . venv/Scripts/activate
python3 -m pip install --upgrade pip
python3 -m pip install -r requirements.txt
```
Create an .env file in which write the settings:
```
SECRET_KEY - secret key to run Django
ALLOWED_HOSTS - Allowed hosts in Django settings
EMAIL_HOST - Host to connect to the mail server
EMAIL_HOST_USER - Login to connect to the mail server
EMAIL_HOST_PASSWORD - Password to connect to the mail server
EMAIL_PORT - Port for connecting to the mail server
EMAIL_USE_SSL - True if using an SSL connection
POSTGRES_URL - URL to connect to PostgreSQL
```

## Run the project on the server:
Navigate to the folder where the manage.py file is located
Run the migrations:
```
python3 manage.py makemigrations
python3 manage.py migrate
```
Run the project:
```
python3 manage.py runserver 0:8000
```
In parallel, you need to start Celery:
```
celery -A LIT_test_task worker --loglevel=info
```


## Endpoints and available request types
/api/v1/auth/signup/ <br>
/api/v1/auth/login/ <br>
/api/v1/auth/verify/ <br>
/api/v1/users/ <br>
/api/v1/users/{id}/ <br>

## Author
[Balchugov Dmitry](https://github.com/Lickan00 "Github page")

## Running project
http://130.193.39.123:8000/swagger/  <br>
http://130.193.39.123:8000/api/v1/auth/signup/  <br>
http://130.193.39.123:8000/api/v1/auth/login/  <br>
http://130.193.39.123:8000/api/v1/auth/verify/  <br>
http://130.193.39.123:8000/api/v1/users/  <br>
