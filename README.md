# Blog
Django by example {Blog}

Проект "Blog" представляет собой простую реализацию функционала блога с использованием Django. Вот основные функции проекта:
* Просмотр списка записей блога
* Полнотекстовой поиск (trigram similarity, по ранжированию, по весу)
* Система комментирования
* Возможность делиться постами через google SMTP
* Система тегов

# Установка

* Создайте .env файл для хранения переменных сред и добавьте в него:
```env
EMAIL_HOST_USER = "your_account"  # необязательно
EMAIL_HOST_PASSWORD = "your_password"  # необязательно
POSTGRESQL_BLOG_PASSWORD = "postgres"
```

* Если вы не указали EMAIL_HOST_USER и EMAIL_HOST_PASSWORD для google smpt в .env. То добавьте в mysite/settings.py:
```python
# Использовать отправку сообщений в терминал
EMAIL_BACKEND = "django.core.mail.backends.console.EmailBackend"
```

* Производим сборку контейнера коммандой:
```
docker-compose up -d --build
```

* Проведите миграцию базы данных:
```
docker-compose exec web python manage.py migrate
```

* Можете загрузить существующие записи блога в базу данных из файла data_for_docker.json:
```
docker-compose exec web python manage.py loaddata data_for_docker.json
```

* Создайте superuser:
```
docker-compose exec webpython manage.py creatsuperuser
```

* Подключение pg_trgm расширения postgresql для triagram similarity поиска:
  1. Вход в интерактивный режим контейнера db
  2. Подключение к базе данных с помощью пользователя postgres
  3. Создание расширения pg_trgm для triagram similarity поиска
```
docker-compose exec -it db bash
psql -U postgres
CREATE EXTENSION pg_trgm;
```

Если вы проделали все пункты выше можете зайти на сайт по адресу http://127.0.0.1:8000/blog/ и увидеть существующие блоги, а по адресу http://127.0.0.1:8000/blog/search/ проверить возможности triagram similarity поиска. 

## Лицензия

Этот проект лицензирован в соответствии с лицензией MIT. Подробности можно найти в файле [LICENSE](LICENSE).

