# Тестовый шаблон докера

Перед запуском меняем при необходимоста имя рабочей дериктории которое по умолчанию `/template`, так же меняем названия
контейнеров которые так же имеют префикс `template`.

Замена  нужна в файлах `docker-compose.yml`, `Makefile`, `/docker/nginx/default.conf`, `/docker/ngnix/Dockerfile`,
`/docker/php-fpm/Dockerfile`

## Запуск

`make build`

Проверяем в браузере [http://localhost:8082/][localhost]


## Конфиг
* **php** = 7.4-fpm при необходимости меняем на нужный в `/docker/php-fpm/Dockerfile`
* **nginx** = 1.17
* **postgres** = 12
* **redis** = 6.2
* **rabbitmq** = 3-management
* **elasticsearch** = 7.5.2



## Возможные проблемы

Если есть проблемы с доступам к папкам, обычно бывает при работе с фреймворками. Заходим на пк через терминал в рабочую
дерикторию и делаем следующее:

`sudo chown -R $USER:$USER . `

`sudo chmod -R 775 . `

Проблемы с доступом `./var/cache` или `./var/log`, добавляем на эти папки права:

`sudo chown -R www-data:www-data ./var/cache`

`sudo chown -R www-data:www-data ./var/log`

