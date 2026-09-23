# 🚀 Развертывание на Koyeb

## Ваш API ключ Koyeb
```
3iv1wyu2326op4okfv2k5905p0v3s8c58gylh89dr2j7nyfbd5413dbbf62safjs
```

## Пошаговая инструкция

### 1. Создать приложение

1. Перейдите: https://app.koyeb.com
2. Нажмите **Create App**
3. Выберите **Docker**

### 2. Настройки Docker

**Docker Image:**
```
yym68686/chatgpt:latest
```

**Service name:**
```
telegram-assistant
```

**Instance type:**
```
Free
```

**Region:**
```
Washington, D.C. (was)
```

### 3. Environment Variables (переменные окружения)

Добавьте следующие переменные:

```bash
BOT_TOKEN=ВАШ_ТОКЕН_ИЗ_BOTFATHER
API=ВАШ_КЛЮЧ_OPENROUTER
BASE_URL=https://openrouter.ai/api/v1
MODEL=amazon/nova-2-lite-v1:free
CUSTOM_MODELS=-all;Free:amazon/nova-2-lite-v1:free,tngtech/tng-r1t-chimera:free,z-ai/glm-4.5-air:free,kwaipilot/kat-coder-pro:free
LANGUAGE=English
SYSTEMPROMPT=You are a helpful AI assistant. Always respond in the same language as the user's question. Be concise and professional.
get_search_results=True
get_url_content=True
download_read_arxiv_pdf=True
WEB_HOOK=https://telegram-assistant-YOUR_APP_NAME.koyeb.app/
```

**ВАЖНО:** После создания приложения, Koyeb даст вам URL вида:
```
https://telegram-assistant-xxx-yyy.koyeb.app/
```

Скопируйте его и вставьте в `WEB_HOOK` (не забудьте `/` в конце)

### 4. Advanced Settings

**Health checks:** Enabled

**Port:** 8080

**Autoscaling:**
- Min instances: 0
- Max instances: 1
- Sleep after: 300 seconds (5 минут)

### 5. Deploy

Нажмите **Deploy**

Ожидайте 2-3 минуты пока приложение развернется.

### 6. Обновить WEB_HOOK

1. После деплоя скопируйте URL вашего приложения
2. Вернитесь в настройки → Environment variables
3. Обновите `WEB_HOOK` с правильным URL
4. Redeploy приложение

### 7. Проверка

Откройте бота: [@Assistants_PTbot](https://t.me/Assistants_PTbot)

Напишите:
```
/start
```

Должно появиться:
```
👋 Здравствуйте!

Чем могу быть полезен?
```

---

## Альтернатива: Deploy через CLI

Если предпочитаете командную строку:

### 1. Установите Koyeb CLI

```bash
# macOS
brew tap koyeb/tap
brew install koyeb-cli

# Linux/macOS (альтернатива)
curl https://www.koyeb.com/install.sh | bash
```

### 2. Авторизуйтесь

```bash
koyeb login
```

Используйте ваш API ключ:
```
3iv1wyu2326op4okfv2k5905p0v3s8c58gylh89dr2j7nyfbd5413dbbf62safjs
```

### 3. Создайте app.yaml

```yaml
# app.yaml
services:
  - name: telegram-assistant
    type: web
    instance_type: free
    regions:
      - was
    scaling:
      min: 0
      max: 1
    docker:
      image: yym68686/chatgpt:latest
    ports:
      - port: 8080
        protocol: http
    env:
      - key: BOT_TOKEN
        value: "ВАШ_ТОКЕН_ИЗ_BOTFATHER"
      - key: API
        value: "ВАШ_КЛЮЧ_OPENROUTER"
      - key: BASE_URL
        value: "https://openrouter.ai/api/v1"
      - key: MODEL
        value: "amazon/nova-2-lite-v1:free"
      - key: CUSTOM_MODELS
        value: "-all;Free:amazon/nova-2-lite-v1:free,tngtech/tng-r1t-chimera:free,z-ai/glm-4.5-air:free,kwaipilot/kat-coder-pro:free"
      - key: LANGUAGE
        value: "English"
      - key: get_search_results
        value: "True"
      - key: get_url_content
        value: "True"
      - key: download_read_arxiv_pdf
        value: "True"
      - key: SYSTEMPROMPT
        value: "You are a helpful AI assistant. Always respond in the same language as the user's question. Be concise and professional."
```

### 4. Deploy

```bash
koyeb app create telegram-assistant -f app.yaml
```

### 5. Получить URL

```bash
koyeb app get telegram-assistant
```

### 6. Обновить WEB_HOOK

```bash
koyeb service update telegram-assistant/telegram-assistant \
  --env WEB_HOOK=https://YOUR_APP_URL.koyeb.app/
```

---

## Мониторинг

### Просмотр логов

```bash
koyeb service logs telegram-assistant/telegram-assistant -f
```

### Статус

```bash
koyeb service get telegram-assistant/telegram-assistant
```

### Перезапуск

```bash
koyeb service redeploy telegram-assistant/telegram-assistant
```

---

## Устранение проблем

### Бот не отвечает

1. **Проверьте логи:**
   ```bash
   koyeb service logs telegram-assistant/telegram-assistant -f
   ```

2. **Проверьте статус:**
   - Зайдите в https://app.koyeb.com
   - Проверьте что сервис `Running`

3. **Проверьте WEB_HOOK:**
   - Должен быть установлен правильный URL
   - URL должен заканчиваться на `/`

### Проблемы с веб-поиском

Убедитесь что:
```
get_search_results=True
```

Бот использует DuckDuckGo - не требуется дополнительных API ключей.

### Бот засыпает

На бесплатном tier Koyeb:
- Бот засыпает после 5 минут неактивности
- Первый запрос может занять 10-20 секунд
- Это нормально для бесплатного tier

---

## Обновление бота

### Обновить код

Docker image `yym68686/chatgpt:latest` обновляется автоматически.

Для применения обновлений:

```bash
koyeb service redeploy telegram-assistant/telegram-assistant
```

Или через веб-интерфейс: Redeploy

---

## Удаление

```bash
koyeb app delete telegram-assistant
```

---

**Готово! Ваш бот работает 24/7 на Koyeb!** ⚡
