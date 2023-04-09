# API YaMDb

## Описание
Проект YaMDb, который выполнен в учебных целяx для курса Яндекс.Практикума, собирает отзывы пользователей на произведения.
Произведения делятся на категории, такие как «Книги», «Фильмы», «Музыка». Например, в категории «Книги» могут быть произведения «Винни-Пух и все-все-все» и «Марсианские хроники», а в категории «Музыка» — песня «Давеча» группы «Жуки» и вторая сюита Баха. Список категорий может быть расширен (например, можно добавить категорию «Изобразительное искусство» или «Ювелирка»).
Произведению может быть присвоен жанр из списка предустановленных
Благодарные или возмущённые пользователи могут оставлять к произведениям текстовые отзывы и ставят произведению оценку в диапазоне от одного до десяти (целое число).
Пользователи могут оставлять комментарии к отзывам.

## Технологии
- Python 3.7
- Django 3.2
- DRF
- PyJWT
- Nginx
- Docker
- PostgreSQL
- Gunicorn

### Запуск проекта.
Для запуска проекта необходим Docker.

- Клонировать репозиторий и перейти в него в командной строке:
```
git clone git@github.com:Rashid-creator-droid/infra_sp2.git
``` 
- Перейти в директорию infra:
```
cd infra
```
- Заполнить файл .env:
>DB_ENGINE=django.db.backends.postgresql\
>DB_NAME= <Имя базы данных>\
>POSTGRES_USER= <Имя пользователя>\
>POSTGRES_PASSWORD= <Пароль базы данных>\
>DB_HOST=db\
>DB_PORT=5432
- Выполнить команду для сборки контейнера:
```
docker-compose up -d
``` 
- Выполнить миграции:
``` 
docker-compose exec web python manage.py migrate
```
- Выполнить сбор статики:
```
docker-compose exec web python manage.py collectstatic --no-input 
```
- Импорт данных из csv:
```
docker-compose exec web python manage.py importdb
```
- Создание суперюзера:
```
docker-compose exec web python manage.py createsuperuser
```
- Документация на приложение доступна по адресу http://localhost/redoc
