# Containerized asynchronous tasks on django web app using celery and redis

Demo on how to handle background processes with Django, Celery, and Docker.



## Steps 

Spin up the containers:

```sh
$ docker-compose up -d --build
```

check sample_tasl.py to change the task operation


Open your browser to http://localhost:5555 to view the Flower dashboard.

<img src="https://github.com/wissemriahi/Django-Celery-Redis--Flower-on-docker-container/blob/master/Readme%20Pics/flower%20dashboard.png" width="600"/>

Trigger a new task:

```sh
$ curl -F type=0 http://localhost:8000/tasks/
```
note you the view function takes the content of 'type'and multiply it by 10 as demo task ,feel free to change the type of taks to be run.
<img src="https://github.com/wissemriahi/Django-Celery-Redis--Flower-on-docker-container/blob/master/Readme%20Pics/curl-1.png"/>


Check the status:

```sh
$ curl http://localhost:8000/tasks/<TASK_ID>/
```
<img src="https://github.com/wissemriahi/Django-Celery-Redis--Flower-on-docker-container/blob/master/Readme%20Pics/curl-2.png"/>

You can also check the dashboard for the status of the tasks 
<img src="https://github.com/wissemriahi/Django-Celery-Redis--Flower-on-docker-container/blob/master/Readme%20Pics/Flower-tasks.png"/>