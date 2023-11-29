#  Kittygram

## Описание

**Kittygram** - это веб-приложение, созданное с использованием Django, которое предоставляет пользователям возможность: 
 
- Загружать фотографии своих котиков. 
- Добавлять описание и достижения к каждому котику. 
- Просматривать галерею фотографий своих котиков. 
- Просматривать список достижений для каждого котика. 
- Добавлять, редактировать и удалять фотографии и достижения. 

## Требования 
Для запуска Котикового Кабинета на вашем сервере, вам потребуется Docker 

## Установка и запуск
Склонируйте репозиторий на ваш сервер: 
 
``` 
https://github.com/NRenat/kittygram_final.git
```

Заполнить **.env** необходимыми данными
```
DB_NAME=django_db
POSTGRES_USER=django_user
POSTGRES_PASSWORD=django_password
POSTGRES_DB=django_db
DB_HOST=db
DB_PORT=5432
SECRET_KEY=ваш секретный django ключ
ALLOWED_HOSTS=
DEBUG=True
```

Запустить Docker контейнер
```
sudo docker compose -f docker-compose.production.yml down
sudo docker compose -f docker-compose.production.yml up -d
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /static/static/
```
