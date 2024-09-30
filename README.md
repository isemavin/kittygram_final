[![Main Kittygram workflow](https://github.com/isemavin/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/isemavin/kittygram_final/actions/workflows/main.yml)

## Проект Kittygram ฅ^•ﻌ•^ฅ 
---
#### Kittygram - это социальная сеть, для любителей котиков, в которой можно делиться фотографиями и достижениями своих питомцев.
---
### Приложение Kittygram использует следующие технологии:
- __Python__ — основной язык программирования.
- __Docker__ — для контейнеризации приложения.
- __GitHub Actions__ — для автоматизации CI/CD процесса.
- __Git__ — как система управления версиями.
---
### Как развернуть проект:
1) Клонируйте репозиторий:
```
git clone git@github.com:isemavin/kittygram_final.git
```
2) Перейдите в корневую папку проекта:
```
cd kittygram_final
```
3) Создайте файл __.env__ и заполните его:
```
POSTGRES_USER=<Имя пользователя>
POSTGRES_PASSWORD=<Пароль>
POSTGRES_DB=<База данных>
DB_HOST=db
DB_PORT=5432
SECRET_KEY=<Секретный ключ django>
DEBUG=<True/False>
ALLOWED_HOSTS=<хосты>
```
4) Запустите docker-compose.production:
```
docker compose -f docker-compose.production.yml up
```
5) Выполните миграции, сбор статики:
```
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /static/static/
```
---
#### Автор проекта: Илья Семавин https://github.com/isemavin