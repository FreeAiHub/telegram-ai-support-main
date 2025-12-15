# Telegram AI Support Bot с OpenRouter

## ✅ Что настроено

Ваш бот уже полностью настроен для работы с **OpenRouter** - сервисом, который предоставляет доступ к десяткам различных AI моделей через единый API!

### 🎯 Преимущества OpenRouter:
- **Множество моделей**: GPT-4, Claude, Gemini, Llama, Mistral и другие
- **Единый API**: Один ключ для всех моделей
- **Гибкие цены**: Платите только за использование
- **Быстрое переключение**: Меняйте модели прямо в чате

## 📋 Текущая конфигурация

### Ваш API ключ настроен:
```
API: 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
```

### Модель по умолчанию:
```
openai/gpt-3.5-turbo
```

### Доступные модели (группы):

#### 🤖 OpenAI
- `openai/gpt-4o` - GPT-4 Omni (самая мощная)
- `openai/gpt-4-turbo` - GPT-4 Turbo
- `openai/gpt-3.5-turbo` - GPT-3.5 (быстрая и дешевая)

#### 🧠 Anthropic Claude
- `anthropic/claude-3.5-sonnet` - Claude 3.5 Sonnet (топовая)
- `anthropic/claude-3-opus` - Claude 3 Opus
- `anthropic/claude-3-haiku` - Claude 3 Haiku (быстрая)

#### 🌟 Google
- `google/gemini-2.0-flash-exp` - Gemini 2.0 Flash (экспериментальная)
- `google/gemini-pro` - Gemini Pro

#### 🦙 Meta Llama
- `meta-llama/llama-3.3-70b-instruct` - Llama 3.3 70B

#### 🎨 Mistral
- `mistralai/mistral-large` - Mistral Large

#### 🔍 DeepSeek
- `deepseek/deepseek-chat` - DeepSeek Chat

#### ⚡ Быстрые модели
- `google/gemini-2.0-flash-thinking-exp` - Gemini с reasoning
- `openai/gpt-4o-mini` - GPT-4 Mini (быстрая)

## 🚀 Запуск бота

```bash
cd /Users/investing/GitHub/Support_agent/telegram-ai-support
python3 bot.py
```

## 💡 Использование

### Основные команды:

1. **Запуск бота**
   ```
   /start
   ```

2. **Переключение модели**
   ```
   /model anthropic/claude-3.5-sonnet
   /model google/gemini-2.0-flash-exp
   /model openai/gpt-4o
   ```

3. **Настройки**
   ```
   /info
   ```
   - Выбор модели из списка
   - Настройки языка
   - Включение/выключение плагинов
   - Предпочтения

4. **Сброс истории**
   ```
   /reset
   ```

### Возможности бота:

✅ **AI-диалоги** - общение с разными моделями
✅ **Веб-поиск** - DuckDuckGo встроен
✅ **Анализ документов** - PDF, TXT, MD, Python
✅ **Анализ изображений** - отправьте фото с вопросом
✅ **Обработка URL** - анализ веб-страниц
✅ **Групповые чаты** - поддержка групп

## 📊 Мониторинг использования

OpenRouter предоставляет детальную статистику:
- Dashboard: https://openrouter.ai/activity
- Расходы по моделям
- История запросов
- Лимиты и баланс

## 💰 Цены моделей (примерные)

Все модели имеют разную стоимость:

**Дешевые (для тестов):**
- GPT-3.5-turbo: ~$0.0005 / 1K токенов
- Claude 3 Haiku: ~$0.00025 / 1K токенов
- Gemini Flash: бесплатно (лимиты)

**Средние:**
- GPT-4o-mini: ~$0.00015 / 1K токенов
- Llama 3.3 70B: ~$0.0008 / 1K токенов

**Премиум:**
- GPT-4o: ~$0.005 / 1K токенов
- Claude 3.5 Sonnet: ~$0.003 / 1K токенов
- Claude 3 Opus: ~$0.015 / 1K токенов

Актуальные цены: https://openrouter.ai/models

## ⚙️ Настройка дополнительных моделей

Чтобы добавить или изменить модели, отредактируйте файл `.env`:

```bash
CUSTOM_MODELS=-all;OpenAI:openai/gpt-4o,openai/gpt-3.5-turbo;Anthropic:anthropic/claude-3.5-sonnet
```

Формат:
- `-all` - удалить все дефолтные модели
- `Группа:модель1,модель2` - создать группу
- Разделитель групп: `;`

Полный список моделей: https://openrouter.ai/models

## 🔧 Продвинутые настройки

### Изменить температуру (креативность)
```bash
temperature=0.7  # 0 = детерминированно, 1 = креативно
```

### Системный промпт
```bash
SYSTEMPROMPT=Ты полезный AI-ассистент технической поддержки
```

### Лимит истории
```bash
PASS_HISTORY=20  # Количество сообщений в памяти
```

## 🛠️ Устранение проблем

### Ошибка "Invalid API Key"
- Проверьте ключ на https://openrouter.ai/keys
- Убедитесь, что есть баланс

### Ошибка "Model not found"
- Проверьте название модели на https://openrouter.ai/models
- Формат: `провайдер/модель`

### Бот не отвечает
```bash
# Проверьте логи
python3 bot.py
```

### Медленные ответы
- Попробуйте более быструю модель:
  - `google/gemini-2.0-flash-exp`
  - `openai/gpt-4o-mini`
  - `anthropic/claude-3-haiku`

## 📱 Групповые чаты

### Добавление в группу:
1. Добавьте бота в группу
2. **Вариант А**: Сделайте бота администратором
3. **Вариант Б**: Отключите Privacy Mode:
   - [@BotFather](https://t.me/BotFather)
   - `/mybots` → выберите бота
   - Bot Settings → Group Privacy → Turn off

### Настройка доступа к группе:
```bash
# В .env добавьте ID группы
GROUP_LIST=-1001234567890
```

Узнать ID группы: [@getidsbot](https://t.me/getidsbot)

## 🌐 Развертывание на сервере

### Docker (рекомендуется)
```bash
# Отредактируйте docker-compose.yml
docker-compose up -d
```

### С webhook (для сервера)
```bash
# В .env добавьте
WEB_HOOK=https://your-domain.com/
```

### Облачные платформы:
- **Koyeb**: Один клик, бесплатно
- **Fly.io**: $5/месяц
- **Railway**: От $5/месяц
- **Render**: Бесплатный tier

## 📚 Полезные ссылки

- OpenRouter Dashboard: https://openrouter.ai
- Документация моделей: https://openrouter.ai/docs
- Цены: https://openrouter.ai/models
- GitHub проекта: https://github.com/yym68686/ChatGPT-Telegram-Bot

## 🆘 Поддержка

- Telegram группа бота: [@t.me/+_01cz9tAkUc1YzZl](https://t.me/+_01cz9tAkUc1YzZl)
- OpenRouter Discord: https://discord.gg/openrouter
- Issues: https://github.com/yym68686/ChatGPT-Telegram-Bot/issues

---

**Готово! Запускайте бота и тестируйте разные модели!** 🚀
