#Dockerize Django REST Framework

Firstly, you should write on your shell `sudo docker-compose run webapi django-admin startproject API .
`

`webapi` is docker-compose's container name.

`API` is project's name.

After that, when code's processes is done, you should see API folder. That is your Django project, not Rest Framework. Now, we will add Rest Framework in our Django.

We will add `'rest_framework'` in API/settings.py --> INSTALLED_APPS
We also change `ALLOWED_HOSTS = []` to `ALLOWED_HOSTS = ['*']`

It is ready to develop.

Now, we create Django app,

`docker-compose up`

Create new terminal and write `docker ps`, and you will see like this

CONTAINER ID        IMAGE                                 COMMAND                  CREATED             STATUS                          PORTS                    NAMES


5ff04b74d281        dockerizedjangorestframework_webapi   "/entrypoint.sh bash…"   14 minutes ago      Up 4 seconds                    0.0.0.0:8001->8001/tcp   dockerizedjangorestframework_webapi_1


After that, we will get container ID and write that code in shell `docker exec -it 5ff04b74d281 bash`. And you will reach the selected container. That mean is our project's shell.

We can write usual Django shell script,

`python manage.py createsuperuser` and fill info. (It will create your super user)

`python manage.py startapp Example` (It will create app which name is Example)