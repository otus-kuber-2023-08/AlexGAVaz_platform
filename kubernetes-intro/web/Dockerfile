# Используйте Python-образ как базовый образ
FROM python:3

# Создайте рабочую директорию внутри контейнера
WORKDIR /app

# Скопируйте файл index.html внутрь контейнера
COPY index.html /app/

# Запуск web-сервера на порту 8000 и отдача содержимого /app
CMD ["python", "-m", "http.server", "8000"]

# Установка UID для запускающего пользователя (1001)
RUN useradd -u 1001 -r -g 0 -d /app -s /sbin/nologin -c "Default Application User" default-user

# Установка прав на рабочую директорию для пользователя UID 1001
RUN chown -R 1001:0 /app

# Переключение на пользователя с UID 1001 при запуске контейнера
USER 1001

# Откройте порт 8000 для внешних подключений
EXPOSE 8000
