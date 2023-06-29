# Blog
Django by example {Blog}

Проект "Blog" представляет собой простую реализацию функционала блога с использованием Django. Вот основные функции проекта:
* Просмотр списка записей блога
* Полнотекстовой поиск
* Система комментирования
* Система тегов

# Установка

* Создаем виртуальное окружение
```
python -m venv .venv
.venv/scripts/activate
```

* Устанавливаем зависимости проекта
```
pip install -r requirements.txt
```

* Создайте .env файл для переменных окружения для smpt и postgresql:
```env
EMAIL_HOST_USER = "Your_email_smpt"
EMAIL_HOST_PASSWORD = "Your_password_for_smpt"
POSTGRESQL_BLOG_PASSWORD = "1243314319"
```

* Можете расскоментировать в educa/settings.py, чтобы использовать вывод smpt сообщений в консоль
```python
EMAIL_BACKEND = "django.core.mail.backends.console.EmailBackend"
```

* Проведите миграцию базы данных:
```
python manage.py migrate
```

* Создайте superuser:
```
python manage.py creatsuperuser
```

* Запуск проекта:
```
python manage.py runserver
```

## Лицензия

Этот проект лицензирован в соответствии с лицензией MIT. Подробности можно найти в файле [LICENSE](LICENSE).

