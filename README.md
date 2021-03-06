# PWS-15_e2_sendgrid

## Доступен в Heroku по адресу:
https://pacific-refuge-00176.herokuapp.com/

## Описание и реализация
Отправляет email с заданными адресатом, текстом и задержкой.
  - Отправка реализована через сервис SendGrid.com
  - Задержка реализована через запуск Thread по сигналу post_save для новой записи Email в базе данных. Задержка ограничена 60-ю секундами (для демонстрации больше не нужно).
  - Все на одной странице: форма запроса данных email и список сообщений (запланированных и уже отправленных).
  - Страница реализована через CreateView, ListView
  - Отправка осуществляется от адреса Ivan.Revyakin@rt.ru

## Установка и запуск (все действия через коммандную строку)
  - скачать проект и перейти в директорию проекта
```
$ git clone https://github.com/LovingFox/PWS-15_e2_sendgrid
$ cd PWS-15_e2_sendgrid
```

  - создать виртуальное окружение
```
$ python -m venv env
```

  - применить виртуальное окружение
```
### Если у вас Linux:
$ source env/bin/activate
### Если у вас Windows:
$ env\Scripts\activate.bat
```

 - установить зависимости
```
$ pip install -r requirements.txt
```

  - создать структуру базы данных
```
$ python manage.py migrate
```

  - создать переменные окружения для работы SendGrid
```
### Если у вас Linux:
$ export SENDGRID_API_KEY=<ключ API>
$ export SENDGRID_TEMPLATE_ID=<id шаблона письма>
$ export SENDGRID_FROM=<поле From письма>
### Если у вас Windows:
$ setx SENDGRID_API_KEY <ключ API>
$ setx SENDGRID_TEMPLATE_ID <id шаблона письма>
$ setx SENDGRID_FROM <поле From письма>
```
В шаблоне используются переменные: data.sent_datetime и data.text

  - запустить сервер
```
$ python manage.py runserver
```

## Использование
http://127.0.0.1:8000/
