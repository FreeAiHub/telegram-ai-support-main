```markdown
# Plan.md
## Технический стек
- Backend: FastAPI (Python 3.10+)
- Frontend: React + TypeScript
- Базы данных: PostgreSQL + Redis
- Микросервисы: Docker + Kubernetes
- AI-модели: GPT-4 Turbo, Claude 3.5 Sonnet, Llama 3.1

## Архитектура
1. AI Gateway (FastAPI)
   - Обработка входящих запросов
   - Маршрутизация к микросервисам
   - Кэширование результатов

2. Trading Service
   - Deal Intelligence
   - Market Analysis
   - Risk Management

3. Compliance Service
   - KYC/AML проверки
   - Sanctions Screening
   - Trade Reporting

4. Notification Service
   - Telegram уведомления
   - Email alerts
   - WebSocket интеграция

## Интеграция AI
- Использование OpenRouter API
- Поддержка нескольких моделей
- Кеширование промежуточных результатов
- Асинхронная обработка запросов
```