# Pro Telegram AI Support Agent

[![Docker](https://img.shields.io/badge/Docker-Ready-blue.svg)](docker-compose.yml)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Telegram Bot](https://img.shields.io/badge/Telegram-Bot-purple.svg)](https://t.me/YOUR_BOT_USERNAME)

**Бизнес-уровневый AI-ассистент для Telegram: автоматизация, поддержка, сложные задачи. Реал-тайм данные, мульти-инструменты, деплой 24/7.**

## 🎯 Бизнес-ценность
- **Автоматизация разработки**: Генерация и выполнение кода, Python REPL, анализ файлов — экономия 80% времени dev.
- **Реал-тайм инсайты**: Поиск через Tavily, Perplexity, SerpAPI — новости, конкуренты, тренды.
- **Поддержка 24/7**: Мультиязык, голосовая обработка, анализ файлов — масштабируемый клиентский сервис.
- **Экспертиза в доменах**: AI, tech, finance, marketing.
- **Низкие затраты**: Free OpenRouter, Koyeb/Fly.io free tier.

**Реальные кейсы:**
1. **Продажи**: \"Актуальные цены конкурентов\" — поиск + анализ.
2. **Разработка**: \"Исправь этот код\" — exec + test.
3. **Поддержка**: Загрузка контракта — QA, извлечение данных.
4. **Маркетинг**: \"Тренды AI 2025\" — полный отчет с источниками.

## 🌟 Ключевой функционал
- **LLM**: GPT-4o-mini, OpenRouter (бесплатно), локальные модели.
- **Поиск и данные**: Tavily, Perplexity, SerpAPI, arXiv, web crawl.
- **Инструменты**: Code generation/execution, Python interpreter, image gen/analysis, file processing.
- **Мультимедиа**: Голос (Whisper), изображения, файлы (PDF/DOCX).
- **Telegram features**: /info, /settings, Markdown formatting (md2tgmd), i18n.
- **AI Engine (aient)**: Плагины для инструментов, models (ChatGPT, Gemini), core logic.

## 📁 Структура проекта
\`\`\`
.
├── bot.py                 # Главный Telegram бот на aiogram
├── config.py              # Конфиг (токены, API ключи из .env)
├── docker-compose.yml     # Деплой Docker (uni-api, bot)
├── Dockerfile*            # Builds для prod
├── aiant/                 # AI ядро
│   ├── core/              # Модели запросов/ответов, utils
│   ├── models/            # ChatGPT, base, audio
│   ├── plugins/           # arXiv, excute_command, image, perplexity, python, search...
│   └── utils/             # Prompts, scripts
├── md2tgmd/               # Конвертер Markdown в Telegram MD (с LaTeX support)
├── docs/                  # Полная документация (RU)
│   ├── БЫСТРЫЙ_СТАРТ.md
│   ├── АВТОНОМНАЯ_РАБОТА_24_7.md
│   ├── ПРИМЕРЫ_ИСПОЛЬЗОВАНИЯ.md
│   └── ... (deploy guides)
├── utils/                 # decorators.py, i18n.py, scripts.py
├── test/                  # Unit тесты
├── assets/                # Логотип, изображения
├── .env.example           # Шаблон env
└── pyproject.toml / uv.lock # Dependencies (uv)
\`\`\`

## 🚀 Быстрый запуск
1. **Клон + env**:
   \`\`\`
   git clone https://github.com/FreeAiHub/pro-telegram.git
   cd pro-telegram
   cp .env.example .env
   # Заполните BOT_TOKEN, OPENROUTER_API_KEY, TAVILY_API_KEY и т.д.
   \`\`\`

2. **Docker**:
   \`\`\`
   docker compose up --build -d
   \`\`\`

3. **Python (uv)**:
   \`\`\`
   uv sync
   uv run python bot.py
   \`\`\`

4. Telegram: Найдите бота, /start.

## ☁️ Деплой Production
- **Koyeb**: Docker image, env secrets, free tier. См. [docs/ФИНАЛЬНАЯ_КОНФИГУРАЦИЯ.md](docs/ФИНАЛЬНАЯ_КОНФИГУРАЦИЯ.md)
- **Fly.io**: fly.toml готов.
- **Docker Compose**: Локально/сервер.

Webhook авто-настройка.

## 📖 Документация
- [Быстрый старт](docs/БЫСТРЫЙ_СТАРТ.md)
- [Автономная работа](docs/АВТОНОМНАЯ_РАБОТА_24_7.md)
- [Примеры](docs/ПРИМЕРЫ_ИСПОЛЬЗОВАНИЯ.md)
- [OpenRouter](docs/OPENROUTER_ИНСТРУКЦИЯ.md)

## 🤝 Контрибьют
1. Fork → clone.
2. \`uv sync & pytest\`
3. PR в main.

**Готово к продакшену! 🚀**

[Оригинал проекта](https://github.com/investing/Support_agent/telegram-ai-support)
