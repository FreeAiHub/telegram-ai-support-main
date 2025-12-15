Я успешно реализовал пошаговую инструкцию по развёртыванию Telegram-агента на Koyeb:

Выполненные шаги:
1. ✅ Создание Web service с Docker
Выбрал Docker как источник для развёртывания

2. ✅ Настройка Docker образа
Указал образ: yym68686/chatgpt:latest

Образ успешно прошёл валидацию

3. ✅ Настройка региона и инстанса
Инстанс: Nano (бесплатный, 0.25 vCPU, 256MB RAM)

Регион: Washington, D.C. (was)

4. ✅ Имя сервиса
Установлено имя: telegram-assistant

5. ✅ Добавление переменных окружения
Добавлены все 10 переменных из инструкции:

BOT_TOKEN: 7775815478:AAH3NK99X4VMJCTo5KYcTw9LBeBa0wYqwE

API: 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

BASEURL: https://openrouter.ai/api/v1

MODEL: amazon/nova-2-lite-v1:free

CUSTOMMODELS: -allFree,amazon/nova-2-lite-v1:free,tngtech/tng-r1t-chimera:free,z-ai/glm-4.5-air:free,kwai/pilot/kat-coder-pro:free

LANGUAGE: English

get_search_results: True

get_url_content: True

download_read_arxiv_pdf: True

SYSTEMPROMPT: You are a helpful AI assistant. Always respond in the same language as the users question. Be concise and professional.

6. ✅ Настройка продвинутых параметров
Порт: 8000 (HTTP)

Health checks: Настроены на порту 8000

Автомасштабирование:

Min instances: 0

Max instances: 1

Idle period: 300 секунд (5 минут)

7. ✅ Развёртывание
Сервис успешно создан и начал развёртывание

8. ✅ URL сервиса
Public URL: https://influential-talya-fg12-2f27524f.koyeb.app/

Текущий статус:
Сервис развёрнут, но находится в состоянии ошибки из-за недействительного BOT_TOKEN. В логах видна ошибка:

text
telegram.error.InvalidToken: The token `7775815478:AAH3NK99X4VMJCTo5KYcTw9LBeBa0wYqwE` was rejected by the server
Что нужно для запуска:
Получить настоящий BOT_TOKEN от @BotFather в Telegram

Добавить переменную WEBHOOK со значением: https://influential-talya-fg12-2f27524f.koyeb.app/

Обновить BOT_TOKEN в настройках сервиса

Redeploy сервиса

Все остальные настройки выполнены корректно согласно инструкции. Сервис готов к работе после замены тестового токена на реальный.