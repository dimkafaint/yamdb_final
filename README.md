API проекта Yamdb
================
## Проект собирает отзывы на различные произведения, с возможностью комментирования и оценки.

#### В проекте используется Python 3, Django 2.2, Django Rest Framework и SQL.

## Как запустить проект:

###### Клонировать репозиторий и перейти в него в командной строке:

git clone https://github.com/dimkafaint/api_yamdb

cd api_yamdb

###### Cоздать и активировать виртуальное окружение:

python3 -m venv venv

source venv/bin/activate

python3 -m pip install --upgrade pip

###### Установить зависимости из файла requirements.txt:

pip install -r requirements.txt

###### Выполнить миграции:

cd api_yamdb

python3 manage.py migrate

###### Наполнить базу данных.

Запустить скрипт api_yamdb\script_csv_to_sql.py из папки проекта.

python script_csv_to_sql.py

###### Запустить проект:

python3 manage.py runserver

[Подробнее](http://127.0.0.1:8000/redoc/)

###### Авторы:
- [Храповицкий Дмитрий](https://github.com/dimkafaint)
- [Кузнецов Андрей](https://github.com/HoodFast)
- [Гайнутдинов Тимур](https://github.com/timurgain)
