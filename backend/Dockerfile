# Используем Python 3.9
FROM python:3.9

# Устанавливаем все необходимые системные зависимости
RUN apt-get update && apt-get install -y dos2unix build-essential libpq-dev libjpeg-dev zlib1g-dev && rm -rf /var/lib/apt/lists/*

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем и устанавливаем зависимости Python
COPY requirements.txt .
RUN dos2unix requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Копируем весь код проекта
COPY . .

CMD ["gunicorn", "kittygram_backend.wsgi:application", "--bind", "0.0.0.0:8000"]