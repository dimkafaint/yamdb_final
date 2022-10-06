### Учебный проект по Docker
## Проект собирает отзывы на различные произведения, с возможностью комментирования и оценки.
### Технологии
Python 3.7
Django 2.2.16
gunicorn 20.0.4
postgresql 13
nginx 1.21.3

### Запуск проекта
- Клонировать проект с GitHub
```
https://github.com/dimkafaint/infra_sp2
```
- Установить Docker
```
https://docs.docker.com/desktop/install/linux-install/
```
- Перейти в каталог с docker-compose
## cd .../infra_sp2/infra
- Создать файл .env и заполнить его:
```
DB_ENGINE=
DB_NAME=
POSTGRES_USER=
POSTGRES_PASSWORD=
DB_HOST=
DB_PORT=
SECRET_KEY=
```
- Собрать контейнер и запустить
```
sudo docker-compose build
sudo docker-compose up -d
```
- *для остановки использовать 
```
sudo docker-compose down -v
```
- Сделать миграции, создать пользователя и собрать статику
```
sudo docker-compose exec web python manage.py migrate
sudo docker-compose exec web python manage.py createsuperuser
sudo docker-compose exec web python manage.py collectstatic --no-input
```

Теперь проект доступен по http://localhost
Админка http://localhost/admin
API http://localhost/api
Наполнение проекта из фикстур:
```
sudo docker-compose exec web python manage.py shell
>>> from django.contrib.contenttypes.models import ContentType
>>> ContentType.objects.all().delete()
>>> quit()
sudo docker-compose exec web python manage.py loaddata fixtures/fixtures.json
```

[Проект таже доступен в сети](http://51.250.29.222/)

###### Авторы:
- [Храповицкий Дмитрий](https://github.com/dimkafaint)


