# Kittygram final
> [kittygram](https://kittygram.servecounterstrike.com/)

## Описание
Данный проект служит интернет-площадкой для котоводов, где владельцы своих котиков могут выставлять их на показ включая имя, цвет, дату рождения и даже фото, а так же отмечать достижения кота. Благодаря данному ресурсу владельцы кошек смогут создать реестр своих питомцев.

## Запуск
Для запуска приложения необходим сервер, рассмотрим на примере сервера под управлением ОС Linux.

1. Подготовим виртуальное окружение в директории проекта создадим файл .env:
```bash
nano .env
```

2. Добавляем следующие переменные:
```nano
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_HOST=db
DB_PORT=5432
SECRET_KEY=...
DEBUG=... # True/False
ALLOWED_HOSTS=127.0.0.1,localhost
```

3. Устанавливаем к Docker утилиту Docker Compose:
```bash
sudo apt update
sudo apt-get install docker-compose-plugin 
```

4. В директорию проекта копируем файл `docker-compose.production.yml` и запускаем Docker Compose:
```bash
sudo docker-compose up
```

## Примеры запросов

Добавить питомца: POST `/cats/add`

Редактировать питомца: PUTCH `/cats/edit`

Просмотр питомца: GET `/cats/{cat_id}`

> Автор проекта junior-разработчик [AxeUnder](https://github.com/AxeUnder)