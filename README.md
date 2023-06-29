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

