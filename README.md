# yamdb_final
yamdb_final

![yamdb_final workflow](https://github.com/Ilia-Abrosimov/yamdb_final/workflows/yamdb_final%20workflow/badge.svg?event=push)

Это API проекта api_yamdb, который собирает отзывы (Review) пользователей на произведения (Title). Произведения делятся на категории (Category). В каждой категории есть произведения: книги, фильмы или музыка. Произведению может быть присвоен жанр (Genres) из списка предустановленных. Новые жанры может создавать только администратор.
Благодарные или возмущённые читатели оставляют к произведениям текстовые отзывы (Review) и выставляют произведению рейтинг.
Сами произведения в api_yamdb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

---
Настроен Continuous Integration и Continuous Deployment для проекта YaMDB: автоматический запуск тестов, обновление образов на Docker Hub и автоматический деплой на боевой сервер при пуше в ветку main

---
<h3> Установка и развертывание </h3>
После выполнения push необходимо зайти на сервер

    $ ssh yc-user@84.201.177.1

Перейти в директорию app

    $ cd app/

Выполнить миграции

    $ docker-compose exec web python manage.py migrate

Собрать статику
    
    $ docker-compose exec web python manage.py collectstatic --noinput
    
Документация по API доступна по адресу\
http://84.201.177.1:1337/redoc/

Доступ к админке\
http://84.201.177.1:1337/admin/

Перечь произведений\
http://84.201.177.1:1337/api/v1/titles/