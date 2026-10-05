# Page Analyzer (SEO-анализатор страниц) 🔍

[![Actions Status](https://github.com/dr-Panakhov/page-analyzer/actions/workflows/hexlet-check.yml/badge.svg)](https://github.com/dr-Panakhov/page-analyzer/actions)
[![Lint Status](https://github.com/dr-Panakhov/page-analyzer/actions/workflows/lint.yml/badge.svg)](https://github.com/dr-Panakhov/page-analyzer/actions)
[![Render](https://img.shields.io/badge/Deployed_on-Render-46E3B7?style=flat-square&logo=render&logoColor=white)](https://python-project-83-j5bd.onrender.com)

**🌐 Живое демо:** [https://python-project-83-j5bd.onrender.com](https://python-project-83-j5bd.onrender.com)

Полноценное веб-приложение для SEO-анализа сайтов. Позволяет добавлять адреса страниц, проверять их доступность (HTTP-статус) и автоматически парсить ключевые SEO-теги (`<h1>`, `<title>`, `<meta name="description">`). 

Проект демонстрирует работу с реляционными базами данных, обработкой HTTP-запросов, парсингом HTML-деревьев и шаблонизацией.

---

### 🛠 Стек технологий

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat-square&logo=postgresql&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap_5-7952B3?style=flat-square&logo=bootstrap&logoColor=white)
![uv](https://img.shields.io/badge/uv-Package_Manager-DE5FE9?style=flat-square)

* **Backend:** Python 3.10+, Flask
* **База данных:** PostgreSQL, psycopg2
* **Парсинг и сеть:** BeautifulSoup4, Requests
* **Инфраструктура & QA:** `uv` (менеджер пакетов), `make`, Ruff (линтер), Gunicorn (WSGI)

---

### 🚀 Установка и локальный запуск

Для работы требуется [uv](https://github.com/astral-sh/uv) и установленный PostgreSQL.

```bash
# 1. Клонировать репозиторий
git clone [https://github.com/dr-Panakhov/page-analyzer.git](https://github.com/dr-Panakhov/page-analyzer.git)
cd page-analyzer

# 2. Установить зависимости
make install

# 3. Настройка окружения
Создайте файл .env в корне проекта и добавьте туда секретный ключ и URL вашей локальной базы данных
SECRET_KEY=your_secret_key
DATABASE_URL=postgresql://postgres:postgres@localhost:5432/page_analyzer

# 4. Подготовка БД и запуск
# 1. Создать таблицы в базе данных
psql -a -d postgresql://postgres:postgres@localhost:5432/page_analyzer -f database.sql

# 2. Запустить сервер для разработки
make dev
После запуска приложение будет доступно по адресу: http://localhost:5000

# 5. Проверка качества кода
make lint
