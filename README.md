# IBENTO · MVP App Eventos

IBENTO is a full-stack web application for event management. It allows users and companies to create, discover, and manage events, buy tickets, and leave ratings.

## Main Features

- User registration and login with JWT authentication.
- Company registration and employee assignment.
- Event creation and event catalog browsing.
- Ticket purchase flow with invoice generation.
- Event ratings and comments.
- Password recovery and reset flow.

## Tech Stack

### Frontend
- React 16.8 (legacy version inherited from the starter template; upgrade has not been completed because it requires coordinated dependency updates and regression testing across the frontend)
- React Router
- Webpack
- Bootstrap / custom styles

### Backend
- Flask
- SQLAlchemy + Flask-Migrate
- JWT (flask-jwt-extended)
- Argon2 password hashing

## Project Structure

- `./src/front` → React frontend.
- `./src/api` → Flask API, models and routes.
- `./migrations` → Database migrations.
- `./public` → Bundled/static assets.

## Requirements

- Python 3.10
- Node.js 16.x
- npm
- Pipenv
- PostgreSQL (recommended) or SQLite

## Environment Setup

1. Copy environment variables:

```bash
cp .env.example .env
```

2. Update `.env` according to your local setup.

Common variables:
- `DATABASE_URL`
- `FLASK_APP`
- `FLASK_ENV`
- `BACKEND_URL` (frontend uses this to call the API)
- `FRONTEND_URL` (used by password reset flow)

## Installation & Run

### Backend (Flask API)

```bash
pipenv install
pipenv run upgrade
pipenv run start
```

Backend runs on `http://localhost:3001`.

### Frontend (React)

In another terminal:

```bash
npm install
npm run start
```

Frontend runs on `http://localhost:3000`.

## Useful Scripts

### npm

```bash
npm run start   # start webpack dev server
npm run build   # production build
```

### pipenv

```bash
pipenv run start    # start Flask app
pipenv run migrate  # generate migration
pipenv run upgrade  # apply migrations
```

## API Overview

Main routes are in `./src/api/routes.py`.

Examples:
- `POST /api/signup`
- `POST /api/login`
- `GET /api/eventos`
- `POST /api/crearevento`
- `POST /api/factura`
- `POST /api/valoracion`
- `POST /api/forgotpassword`
- `POST /api/password-reset`

## Notes

- This repository currently does not include automated test suites.
- The app includes deployment-related files for Render/Procfile-based setups.
