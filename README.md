# PayGo_Uz

Демо-проект платёжной панели для разработки и тестирования.

## Что есть в репозитории
- `frontend/index.html` — адаптивная панель на русском языке.
- `backend/app/main.py` — минимальный API на FastAPI для демонстрационных данных.
- `backend/requirements.txt` — зависимости backend.
- `backend/.env.example` — пример переменных окружения (без секретов).

## Важно
Это **не готовая платёжная система**. Балансы, ордера и графики демонстрационные. Интеграции Uzcard/Humo/Payme и криптовалютных операций не подключены. Не используйте макет для хранения данных банковских карт, ключей, seed-фраз или приватных ключей.

Перед приёмом реальных платежей необходимо:
1. Определить законную модель деятельности и необходимые разрешения в Узбекистане.
2. Заключить договор с соответствующим лицензированным платёжным провайдером.
3. Реализовать серверную проверку подписей вебхуков, идемпотентность и сверку транзакций.
4. Хранить секреты только в защищённых переменных окружения/secret manager.
5. Добавить аутентификацию, роли, аудит, rate limiting, резервное копирование и тесты.

## Запуск интерфейса
Откройте `frontend/index.html` в браузере.

## Запуск API
Python 3.11+:
```bash
cd backend
python -m venv .venv
# Windows: .venv\\Scripts\\activate
# macOS/Linux:
source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```
API: `http://127.0.0.1:8000`
Документация: `http://127.0.0.1:8000/docs`

## Загрузка на GitHub
Создайте пустой репозиторий `PayGo_Uz`, затем:
```bash
git init
git add .
git commit -m "Initial PayGo_Uz demo"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/PayGo_Uz.git
git push -u origin main
```
