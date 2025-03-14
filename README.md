
## Tecnhologies

- Python 3.11
- Django 4.0
- Django REST framework 3.14
- Nginx
- Docker
- Postgres



```text
git clone git@ithub.com/Gordenator/foodgram
```

- Подключитесь к вашему серверу:

```text
ssh <пользователь сервера>@<IP-адрес сервера>
```

- Установите Docker на вашем сервере

```text
sudo apt install docker.io
```

- Установите Docker Compose (для Linux)

```text
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

- Получите права для docker-compose

```text
sudo chmod +x /usr/local/bin/docker-compose
```

- Создайте директорию проекта (желательно в вашей домашней директории)

```text
mkdir foodgram && cd foodgram/
```

- Создайте env-файл:

```text
touch .env
```

- Заполните env-файл следующим образом:

```text
DEBUG=False
SECRET_KEY=<Ваша_какая-нибудь_длинная_строка>
ALLOWED_HOSTS=<Ваш_хост>
CSRF_TRUSTED_ORIGINS=https://<Ваш_хост>
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=<Ваш_пароль>
DB_HOST=foodgram-db
DB_PORT=5432
```

- Скопируйте файлы из 'infra/' (на вашей локальной машине) на ваш сервер:

```text
scp -r infra/* <пользователь сервера>@<IP-адрес сервера>:/home/<пользователь сервера>/foodgram/
```

- Запустите docker-compose

```text
sudo docker-compose up -d
```

Подождите несколько секунд...
Ваш сервис работает!

**Приятного аппетита!**


```text
sudo docker exec -it foodgram-app python manage.py createsuperuser
```

И если хотите, вы можете использовать список ингредиентов, предложенный нами, для написания рецептов.
Загрузите его в базу данных с помощью следующей команды:

```text
sudo docker exec -it foodgram-app python manage.py loaddata data/dump.json
```

