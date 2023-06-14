# Требования

- Установленные docker и docker-compose

# Установка

1. Скопировать репозиторий в нужную папку: `git clone git@github.com:UnsealedOne/docker-laravel-boilerplate.git <project-name>`
2. Перейти в папку проекта: `cd <project-name>`
3. Отредактировать файл `.env` указав названия базы данных и параметры доступа к ней
4. Удалить папку .git: `rm -rf .git`
5. Удалить файл .gitkeep из папки database: `rm database/.gitkeep`
6. Удалить файл .gitkeep из папки www: `rm www/.gitkeep`
7. Для первого запуска docker-compose ввести команду: `docker-compose up --build -d`, дождаться пока контейнеры соберутся и запустятся. В дальнейшем можно запускать командой `docker-compose start`. Для остановки соответственно выполнить `docker-compose stop`.

# Использование

Теперь можно установить laravel в папку `www` (параметры для подключения к базе данных можно взять из файла `.env`, в параметре `DB_HOST` указать `mariadb`). После установки laravel и запуска контейнеров сайт будет доступен по адресу `http://localhost`

# Консоль

Для подключения к контейнеру с установленным приложением можно воспользоваться командой `docker-compose exec app bash`

# Дополнительные сервисы

1. Phpmyadmin доступна по адресу `http://localhost:8001/`
2. Mailhog доступен по адресу: `http://localhost:8025/`

Для использования Mailhog в конфиге laravel нужно указать следующие параметры:
```
MAIL_MAILER=smtp
MAIL_HOST=mailhog
MAIL_PORT=1025
```
