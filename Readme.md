# 🤖 Party Bot

Telegram-бот для демотиваторов, шакал-качества и стикеров.

## Деплой на Render

1. Залей репозиторий на GitHub
2. На [render.com](https://render.com) → **New +** → **Web Service**
3. Подключи репозиторий
4. Настройки:
   - **Name:** party-bot
   - **Environment:** Python 3
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `gunicorn bot:app --threads 2 --bind 0.0.0.0:$PORT --timeout 120`
   - **Plan:** Free (или Starter)
5. Во вкладке **Environment** добавь переменные:
   - `BOT_TOKEN` — токен от @BotFather
   - `SUPERGROUP_ID` — ID супергруппы для логов
   - `ACCESS_ADMINS`, `ACCESS_BLACKLIST`, `ACCESS_SELECTED` — через запятую
6. **Deploy**

## Локальный запуск

```bash
pip install -r requirements.txt
echo "YOUR_TOKEN" > info/token
python bot.py
