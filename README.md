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


