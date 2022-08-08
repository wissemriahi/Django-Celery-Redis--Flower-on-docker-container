# Containerized asynchronous tasks on django web app using celery and redis

Demo on how to handle background processes with Django, Celery, and Docker.



## Steps 

Spin up the containers:

```sh
$ docker-compose up -d --build
```

check sample_tasl.py to change the task operation


Open your browser to http://localhost:5555 to view the Flower dashboard.

[![alt text](https://github.com/wissemriahi/Django-Celery-Redis--Flower-on-docker-container/blob/master/Readme%20Pics/ flower%20dashboard.png"demo")]

Trigger a new task:

```sh
$ curl -F type=0 http://localhost:8000/tasks/
```
note you the view function takes the content of 'type'and multiply it by 10 as demo task ,feel free to change the type of taks to be run. 

Check the status:

```sh
$ curl http://localhost:8000/tasks/<TASK_ID>/
```
