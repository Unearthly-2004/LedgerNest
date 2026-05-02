# LedgerNest

LedgerNest is a business ledger app with:

- a React frontend
- an Express + TypeScript backend
- Gemini-powered chat commands
- Telegram admin and client bot support

## Project structure

- `frontend` - web app
- `backend` - API server

## Run locally

### Frontend

```bash
cd frontend
npm install
npm start
```

Runs on `http://localhost:3000`

### Backend

```bash
cd backend
npm install
npm run dev
```

Runs on `http://localhost:8001`

## Required backend env

Set these in `backend/.env`:

```env
SUPABASE_URL=
SUPABASE_SERVICE_ROLE_KEY=
GEMINI_API_KEY=
GEMINI_MODEL=gemini-2.5-flash
NODE_ENV=development
PORT=8001
CORS_ORIGINS=http://localhost:3000
BACKEND_URL=http://localhost:8001
FRONTEND_URL=http://localhost:3000
CLIENT_PORTAL_SIGNING_SECRET=
TELEGRAM_ADMIN_BOT_TOKEN=
TELEGRAM_CLIENT_BOT_TOKEN=
TELEGRAM_ADMIN_BOT_USERNAME=LedgerNestAdminBot
TELEGRAM_CLIENT_BOT_USERNAME=LedgerNestClientBot
```

## Telegram

In local development, keep `NODE_ENV=development` so Telegram runs in polling mode.

Create two bots with `@BotFather`:

- `LedgerNestAdminBot`
- `LedgerNestClientBot`

Then add their tokens and usernames to `backend/.env`.

## Health check

Backend health:

```bash
http://localhost:8001/health
```

Frontend:

```bash
http://localhost:3000
```
