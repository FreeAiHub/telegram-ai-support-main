# 🤖 Telegram AI Support Bot

## ✅ Статус: Готов к работе!

Ваш AI-бот для Telegram полностью настроен и запущен с использованием **OpenRouter**.

---

## 🎯 Краткая информация

| Параметр | Значение |
|----------|----------|
| **Telegram Bot** | [@Assistants_PTbot](https://t.me/Assistants_PTbot) |
| **API Провайдер** | OpenRouter |
| **Модель по умолчанию** | openai/gpt-3.5-turbo |
| **Статус** | 🟢 Работает |
| **Язык интерфейса** | Русский |

---

## 🚀 Быстрый запуск

### Запуск бота:
```bash
cd /Users/investing/GitHub/Support_agent/telegram-ai-support
python3 bot.py
```

### Остановка бота:
```bash
# Нажмите Ctrl+C в терминале
```

---

## 💡 Возможности

✅ **AI-диалоги** с множеством моделей (GPT-4, Claude, Gemini, Llama)
✅ **Веб-поиск** через DuckDuckGo
✅ **Анализ документов** (PDF, TXT, MD, Python)
✅ **Анализ изображений** и голосовых сообщений
✅ **Обработка URL** и веб-страниц
✅ **Групповые чаты** с изоляцией диалогов
✅ **Русский интерфейс**

---

## 🎮 Команды бота

| Команда | Описание |
|---------|----------|
| `/start` | Начать работу с ботом |
| `/info` | Настройки, смена модели, языка |
| `/model <название>` | Быстрая смена модели |
| `/reset` | Очистить историю диалога |

### Примеры смены модели:
```
/model openai/gpt-4o
/model anthropic/claude-3.5-sonnet
/model google/gemini-2.0-flash-exp
```

---

## 🤖 Доступные модели

Настроено **8 групп моделей**:

### 🔵 OpenAI
- `openai/gpt-4o` - GPT-4 Omni
- `openai/gpt-4-turbo` - GPT-4 Turbo
- `openai/gpt-3.5-turbo` - GPT-3.5 (по умолчанию)

### 🟣 Anthropic
- `anthropic/claude-3.5-sonnet` - Claude 3.5 Sonnet
- `anthropic/claude-3-opus` - Claude 3 Opus
- `anthropic/claude-3-haiku` - Claude 3 Haiku

### 🔴 Google
- `google/gemini-2.0-flash-exp` - Gemini 2.0 Flash
- `google/gemini-pro` - Gemini Pro

### 🟠 Meta
- `meta-llama/llama-3.3-70b-instruct` - Llama 3.3 70B

### 🟡 Mistral
- `mistralai/mistral-large` - Mistral Large

### 🟢 DeepSeek
- `deepseek/deepseek-chat` - DeepSeek Chat

### ⚡ Быстрые модели
- `google/gemini-2.0-flash-thinking-exp` - Gemini с reasoning
- `openai/gpt-4o-mini` - GPT-4 Mini

Полный список: https://openrouter.ai/models

---

## 📂 Структура проекта

```
telegram-ai-support/
├── bot.py                      # Главный файл бота
├── config.py                   # Конфигурация
├── .env                        # Переменные окружения (ваши ключи)
├── README_RU.md               # Эта инструкция
├── БЫСТРЫЙ_СТАРТ.md           # Краткая памятка
├── OPENROUTER_ИНСТРУКЦИЯ.md   # Подробная инструкция по OpenRouter
└── ИНСТРУКЦИЯ_ЗАПУСКА.md      # Полное руководство по настройке
```

---

## ⚙️ Текущие настройки (.env)

```bash
# Telegram
BOT_TOKEN=ВАШ_ТОКЕН_ИЗ_BOTFATHER

# OpenRouter API
BASE_URL=https://openrouter.ai/api/v1
API=sk-or-v1-***
MODEL=openai/gpt-3.5-turbo

# Функции
get_search_results=True          # Веб-поиск включен
get_url_content=True             # Обработка URL включена
download_read_arxiv_pdf=True     # Анализ PDF включен
LANGUAGE=Russian                 # Русский интерфейс
```

---

## 📊 Мониторинг

### OpenRouter Dashboard
- **Активность**: https://openrouter.ai/activity
- **Расходы**: Отслеживание по моделям
- **Баланс**: Проверка остатка средств

### Логи бота
```bash
# Запустите бота в терминале чтобы видеть логи:
python3 bot.py
```

---

## 🔧 Дополнительные настройки

### Ограничение доступа (Whitelist)
```bash
# В .env добавьте:
whitelist=123456789,987654321  # Telegram User IDs
```

Узнать свой ID: [@userinfobot](https://t.me/userinfobot)

### Настройка админов
```bash
ADMIN_LIST=123456789  # Только админы могут менять настройки через /info
```

### Групповые чаты
```bash
GROUP_LIST=-1001234567890  # ID группы через запятую
```

Узнать ID группы: [@getidsbot](https://t.me/getidsbot)

---

## 🛠️ Устранение проблем

### Бот не запускается
1. Проверьте Python версию: `python3 --version` (нужна 3.11+)
2. Переустановите зависимости: `pip install -r requirements.txt`

### Бот не отвечает в Telegram
1. Убедитесь, что бот запущен: `python3 bot.py`
2. Проверьте OpenRouter баланс: https://openrouter.ai
3. Проверьте логи в терминале

### Ошибки API
- **Invalid API Key**: Проверьте ключ в `.env`
- **Model not found**: Используйте формат `провайдер/модель`
- **Rate limit**: Подождите или переключитесь на другую модель

---

## 📚 Документация

- 📖 [БЫСТРЫЙ_СТАРТ.md](БЫСТРЫЙ_СТАРТ.md) - для быстрого начала работы
- 📘 [OPENROUTER_ИНСТРУКЦИЯ.md](OPENROUTER_ИНСТРУКЦИЯ.md) - подробно про OpenRouter
- 📕 [ИНСТРУКЦИЯ_ЗАПУСКА.md](ИНСТРУКЦИЯ_ЗАПУСКА.md) - полное руководство

---

## 🌐 Полезные ссылки

- **OpenRouter**: https://openrouter.ai
- **Модели и цены**: https://openrouter.ai/models
- **Документация**: https://openrouter.ai/docs
- **GitHub проекта**: https://github.com/yym68686/ChatGPT-Telegram-Bot
- **Telegram группа**: https://t.me/+_01cz9tAkUc1YzZl

---

## 🎉 Готово к работе!

Ваш бот уже запущен и готов отвечать на вопросы!

1. Откройте [@Assistants_PTbot](https://t.me/Assistants_PTbot)
2. Отправьте `/start`
3. Начните диалог!

---

## 📝 Лицензия

GPLv3 - свободное ПО с открытым кодом

**Важно**: Не публикуйте файл `.env` с вашими API ключами!

---

*Создано для технической поддержки и AI-ассистирования* 🤖
