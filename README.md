# Привет! Меня зовут Степан

## О себе

Backend-разработчик, специализируюсь на **Python** и **FastAPI**. Создаю полнофункциональные веб-приложения с фокусом на чистую архитектуру, REST API и интеграцию с внешними сервисами, а также интегрирую LLM в рабочие процессы.

Прохожу полный цикл разработки: от проектирования до деплоя на production. Люблю создавать переиспользуемые решения и автоматизировать процессы.

# 📂 Портфолио проектов | Backend & AI Engineering

Коллекция моих проектов: REST API, веб-приложения, AI-агенты, RAG-системы, парсинг данных, интеграции с LLM.

## 🚀 Production проекты

Все проекты развёрнуты и доступны на [stefandev.ru](https://stefandev.ru)

---

### 1️⃣ FamilyLog — семейный дневник на AI
**Репозиторий:** [github.com/JustStepan/familylog](https://github.com/JustStepan/familylog)  
**Страница проекта:** [stefandev.ru/familylog.html](https://stefandev.ru/familylog.html)

**Описание:** Личный production-пайплайн, который превращает голосовые сообщения, фото и текст из Telegram в структурированные Markdown-заметки в Obsidian vault. Работает полностью локально — никаких облачных зависимостей.

**Что решает:** Автоматизирует ведение семейного дневника: члены семьи пишут боту как обычно, всё автоматически попадает в Obsidian с тегами, связями и frontmatter. STT на русском языке, описание фото, интеграция с Google Calendar.

**Технологии:** Python, aiogram, LangGraph, LM Studio, SQLite, async SQLAlchemy, Pydantic v2, onnx-asr (GigaAM v3), Qwen3.5-VL, Qwen3.5-35B-A3B, Obsidian Local REST API, Google Calendar API, httpx, Loguru, uv

**Основной функционал:**
- Telegram-бот с 4 типами записей: заметка, дневник, событие, задача
- STT транскрипция голосовых через GigaAM v3 (офлайн, русский язык)
- Описание фотографий через мультимодальную Qwen3.5-VL
- LangGraph-агент генерирует JSON: заголовок, теги, связанные заметки, резюме
- Запись в Obsidian через Local REST API с обновлением контекстных файлов
- Интеграция с Google Calendar для событий
- Еженедельные сводки с автоматической отправкой в Telegram

---

### 2️⃣ RAG System — локальная AI-база знаний по документам
**Репозиторий:** [github.com/JustStepan/RAG_SYSTEM](https://github.com/JustStepan/RAG_SYSTEM)  
**Страница проекта:** [stefandev.ru/rag-system.html](https://stefandev.ru/rag-system.html)

**Описание:** Локальная RAG-система для интеллектуального поиска по PDF-документам с LangGraph-агентом. Векторизует документы в ChromaDB, отвечает на вопросы с указанием источников, при отсутствии ответа переключается на веб-поиск через Tavily.

**Что решает:** Позволяет задавать вопросы по любым загруженным документам и получать ответы с цитированием. Всё локально — данные не покидают машину. В перспективе — поддержка DOCX, EPUB, TXT и веб-страниц.

**Технологии:** Python, LangGraph, LangChain, ChromaDB, LM Studio, Tavily Search API, Pydantic Settings, Loguru, uv

**Основной функционал:**
- Инкрементальная индексация PDF (новые документы добавляются без переиндексации)
- Семантический поиск через ChromaDB (top-5 по cosine similarity)
- LangGraph-агент с MemorySaver — помнит контекст всего диалога
- Fallback на Tavily веб-поиск при отсутствии ответа в базе
- Цитирование источников в ответах

---

### 3️⃣ REST API для автоматизированного подбора вакансий
**Ссылка:** [stefandev.ru/habr-vacancies](https://stefandev.ru/habr-vacancies/)

**Описание:** Система парсинга и умного подбора IT-вакансий с Habr.Career. Парсит 1000+ актуальных вакансий, сохраняет в PostgreSQL, предоставляет API для поиска по навыкам, уровню специалиста и фильтрации новых/переопубликованных позиций. Реализована JWT-аутентификация и функционал избранного.

**Что решает:** Помогает разработчикам находить релевантные вакансии с умной фильтрацией и персонализацией. В разработке — AI-модуль для автоматического сопоставления вакансий с навыками пользователя.

**Технологии:** FastAPI, PostgreSQL, Beautiful Soup, Docker, React, Nginx, JWT, pytest

**Основной функционал:**
- Асинхронный парсинг вакансий с Habr.Career
- REST API с поиском по навыкам и уровню
- JWT-аутентификация и управление избранным
- Покрытие тестами (pytest) основных функций парсера
- Деплой на production с Docker и Nginx

---

### 4️⃣ Утилита для модификации epub-файлов
**Ссылка:** [stefandev.ru/azb-epub-header-changer](https://stefandev.ru/azb-epub-header-changer/)

**Описание:** Веб-утилита для автоматического изменения структуры заголовков в EPUB-файлах. Парсит файл через Beautiful Soup и EpubLib Framework, изменяет уровни заголовков как в теле книги, так и в оглавлении.

**Что решает:** Решает проблему некорректной иерархии заголовков в электронных книгах — критично для построения RAG-систем и навигации по книге.

**Технологии:** FastAPI, Docker, Beautiful Soup, EpubLib Framework, Nginx

**Основной функционал:**
- Парсинг и модификация EPUB-файлов
- Автоматическое обновление оглавления (TOC)
- Веб-интерфейс для загрузки и скачивания файлов

---

## 📚 Учебные проекты

*(Этот раздел может быть будет заполнен проектами с Flask и Django из курса Яндекс.Практикум)*

---

## 🛠️ Технологический стек

**Backend:** Python, FastAPI, Django, Flask  
**AI / LLM Engineering:** LangGraph, LangChain, RAG-системы,  OpenRouter API, prompt engineering etc.
**Агентные системы:** LangGraph StateGraph, tool calling, MemorySaver, ReAct pattern  
**Векторные БД:** ChromaDB, pgVector 
**STT / Vision:** onnx-asr, GigaAM v3, Qwen3.5-VL  
**Базы данных:** PostgreSQL, SQLite, SQLAlchemy (async), Alembic  
**Тестирование:** pytest  
**DevOps:** Docker, Nginx, GitHub Actions (CI/CD)  
**Frontend:** React, JavaScript (базовый уровень)
**Парсинг:** Beautiful Soup  
**Инструменты:** uv, Pydantic v2, Loguru, httpx

---

## 📫 Контакты

- **Портфолио:** [stefandev.ru](https://stefandev.ru)
- **GitHub:** [@JustStepan](https://github.com/JustStepan)
- **Email:** danilenkostepan@gmail.com
- **Telegram:** [@StefanDKO](https://t.me/StefanDKO)

💡 **Открыт к интересным предложениям и сотрудничеству!**

---

## 📊 GitHub Stats

[![GitHub Streak](https://streak-stats.demolab.com?user=JustStepan&theme=dark&hide_border=true&date_format=j%20M%5B%20Y%5D)](https://git.io/streak-stats)
---
![followers](https://img.shields.io/github/followers/JustStepan?style=social)
![stars](https://img.shields.io/github/stars/JustStepan?style=social)
---
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white)
![Beautiful Soup](https://img.shields.io/badge/Beautiful_Soup-43B02A?style=for-the-badge)
---
![Profile Views](https://komarev.com/ghpvc/?username=JustStepan&color=blue)
---
