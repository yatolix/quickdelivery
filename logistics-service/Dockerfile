FROM python:3.13-slim

# Устанавливаем рабочую директорию
WORKDIR /app

COPY requirements.txt requirements.txt
RUN apt-get update && apt-get install -y python3 && pip install -r requirements.txt

COPY . .

# Определяем команду для запуска приложения
CMD ["python", "app.py"]