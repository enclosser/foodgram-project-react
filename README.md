![example workflow](https://github.com/Andrey-oss-ai/foodgram-project-react/actions/workflows/foodgram_workflow.yml/badge.svg)

[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat-square&logo=Django%20REST%20Framework)](https://www.django-rest-framework.org/)
[![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-464646?style=flat-square&logo=PostgreSQL)](https://www.postgresql.org/)
[![Nginx](https://img.shields.io/badge/-NGINX-464646?style=flat-square&logo=NGINX)](https://nginx.org/ru/)
[![gunicorn](https://img.shields.io/badge/-gunicorn-464646?style=flat-square&logo=gunicorn)](https://gunicorn.org/)
[![docker](https://img.shields.io/badge/-Docker-464646?style=flat-square&logo=docker)](https://www.docker.com/)
[![GitHub%20Actions](https://img.shields.io/badge/-GitHub%20Actions-464646?style=flat-square&logo=GitHub%20actions)](https://github.com/features/actions)
[![Yandex.Cloud](https://img.shields.io/badge/-Yandex.Cloud-464646?style=flat-square&logo=Yandex.Cloud)](https://cloud.yandex.ru/)

# Foodgram

Foodgram - сервис для публикации рецептов, работающий как web сервис, 
так и через api. Пользователи прошедшие авторизацию могут добавлять 
рецепты других пользователей в избранное, подписываться на понравившихся
авторов и формировать список покупок из рецептов.

##Разработка

Это первая часть реализации дипломного проекта, в рамках которого, frontend был
предоставлен изначально. Задачей являлась разрабока backend.

#Подготовка и запуск проекта
Требуется создать .env файл и задайте в нем переменные: 
```
SECRET_KEY=<Secret key of Django project>
DB_ENGINE=<django.db.backends.postgresql>
POSTGRES_PASSWORD=<Postgress pass>
DB_NAME=<Database name>
POSTGRES_USER=<Postgress user>
DB_HOST=<Host with Database>
DB_PORT=<Database port>
```
На данный момент проект запускается из папки ./infra командой
```
docker-compose up
```
В результате будет создано 4 контейнера Docker:
infra_nginx_1
infra_frontend_1
infra_backend_1
infra_db_1

После успешной сборки на сервере выполните команды
(только после первого деплоя):

Собрать статические файлы:
```
sudo docker-compose exec backend python manage.py collectstatic --noinput
```
Выполнить миграции:
```
sudo docker-compose exec backend python manage.py migrate --noinput
```
Загрузить подготовленный список ингредиентов:
```
sudo docker-compose exec backend python manage.py loaddata fixtures/ingredients.json
```
Создать суперпользователя Django:
```
sudo docker-compose exec backend python manage.py createsuperuser
```
Проект будет доступен по адресу http://localhost/

##Для работы с workflow требуется добавить в Secrets Github переменные окружения:
```
DOCKER_PASSWORD=<пароль от DockerHub>
DOCKER_USERNAME=<имя пользователя DockerHub>
```

##Технологии
В ходе разработки использованы технологии

Django

Docker

Nginx

PostgresSQL

##Автор

andreu-antonov@yandex.ru


