# 🚀 PgSnapSafe
[English](README.md) | Русский

**PgSnapSafe** – это автоматизированный сервис резервного копирования PostgreSQL с возможностью загрузки бэкапов в S3 и уведомлениями по email. Позволяет удобно настраивать расписание бэкапов и управлять хранимыми копиями через конфигурационный файл `.yml`.

## 📌 Возможности

✅ Автоматическое резервное копирование PostgreSQL  
✅ Гибкое расписание бэкапов (через YAML)  
✅ Ограничение количества хранимых копий  
✅ Поддержка загрузки в **AWS S3 / MinIO**  
✅ Email-уведомления о статусе бэкапа  
✅ Встроенный **health check**

## 🛠 Установка

### 1️⃣ Клонирование репозитория
```bash
git clone https://github.com/yourusername/PgSnapSafe.git
cd PgSnapSafe
```

### 2️⃣ Настройка переменных окружения
Создай `.env` файл и добавь в него настройки подключения к базе данных и S3:

```ini
# PostgreSQL
POSTGRESQL_HOST=your-postgresql-host
POSTGRESQL_PORT=5432
POSTGRESQL_USER=your-user
POSTGRESQL_PASSWORD=your-password
POSTGRESQL_DBNAME=your-database

# Директория для хранения бэкапов
DIRECTORY_BACKUP_PATH=/app/db_backups

# S3 (если используется)
S3_BUCKET_NAME=your-bucket
S3_REGION=your-region
S3_ACCESS_KEY=your-access-key
S3_SECRET_KEY=your-secret-key
S3_ENDPOINT=your-s3-endpoint

# Email (если используется)
SMTP_HOST=smtp.your-email.com
SMTP_PORT=587
SMTP_USER=your-email@example.com
SMTP_PASS=your-password
SMTP_SENDER_SIGN=PgSnapSafe
EMAIL_DELIVERY=your-notify-email@example.com
```

### 3️⃣ Настройка расписания бэкапов
Открой `config.yml` и укажи время выполнения бэкапов и число хранимых копий:

```yaml
backup:
  times:
    - "02:00"
    - "14:00"
  keep_copies: 5

s3: true        # Включить загрузку в S3
smtp: true      # Включить email-уведомления
health_check: true  # Проверка работоспособности при запуске
```

### 4️⃣ Запуск через Docker
```bash
docker-compose up -d
```

## 🚀 Использование

### Запуск вручную
```bash
docker exec -it postgresdump /usr/local/bin/postgresdump
```

### Остановка сервиса
```bash
docker-compose down
```

## 📜 Лицензия

Проект распространяется под **MIT License**. Используйте свободно!

## 💚Поддержать проект донатом 💚
USDT TRC20
```bash
TMpytFwhc5BaWpUeBkB9BdJndoHb7nFWkU
```
