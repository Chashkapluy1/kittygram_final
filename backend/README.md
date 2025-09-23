# Kittygram: Социальная сеть для ваших питомцев

![Kittygram CI/CD](https://github.com/Chashkapluy1/kittygram_final/actions/workflows/main.yml/badge.svg)

Kittygram — это учебный проект, представляющий собой API для социальной сети, где пользователи могут делиться фотографиями своих котиков. Проект упакован в Docker-контейнеры и разворачивается на удаленном сервере с помощью CI/CD на базе GitHub Actions.

---

### Стек технологий

- **Backend:** Python 3.9, Django, Django REST Framework
- **Frontend:** React.js
- **База данных:** PostgreSQL
- **Веб-сервер:** Nginx
- **Контейнеризация:** Docker, Docker Compose
- **CI/CD:** GitHub Actions

---

### Как развернуть проект

1.  **Склонируйте репозиторий на ваш сервер:**
    ```bash
    git clone https://github.com/Chashkapluy1/kittygram_final.git
    cd kittygram_final
    ```

2.  **Создайте и заполните файл `.env`:**
    В корневой директории проекта создайте файл `.env` на основе `example/.env.example` и заполните его своими данными.

3.  **Запустите проект с помощью Docker Compose:**
    ```bash
    sudo docker compose -f docker-compose.production.yml up -d
    ```

4.  **Выполните миграции и соберите статику:**
    ```bash
    sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
    sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic --no-input
    ```
Проект будет доступен по вашему IP-адресу или доменному имени на порту 9000.

---

### Заполнение файла `.env`

```env
# Переменные для PostgreSQL
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password

# Переменные для подключения Django к БД
DB_NAME=kittygram
DB_USER=kittygram_user
DB_PASSWORD=kittygram_password
DB_HOST=db
DB_PORT=5432

# Настройки Django
SECRET_KEY='ваш-секретный-ключ'
DEBUG=False
ALLOWED_HOSTS='https://kittygram-final10.duckdns.org,127.0.0.1,localhost'

# Настройки CORS
CORS_ALLOWED_ORIGINS='http://localhost:3000,https://kittygram-final10.duckdns.org'
```

---

### Автор

- **Имя:** Павел Лагерев
- **GitHub:** [Chashkapluy1](https://github.com/Chashkapluy1)
