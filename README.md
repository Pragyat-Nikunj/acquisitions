# Acquisition API

A robust Node.js Express API for managing acquisitions, featuring secure authentication, user management, rate limiting, and production-ready Docker deployment.

## Features

- **User Authentication**: Secure signup, sign-in, and sign-out with JWT.
- **Role-Based Access Control**: Admin and user roles with protected endpoints.
- **Rate Limiting & Bot Detection**: Powered by Arcjet for enhanced security.
- **Database Integration**: Uses Drizzle ORM with Neon/Postgres.
- **Dockerized**: Multi-stage Dockerfile for efficient builds.
- **CI/CD**: GitHub Actions for testing, linting, formatting, and Docker image publishing.
- **Logging**: Winston-based structured logging.
- **Validation**: Zod schemas for request validation.

## Getting Started

### Prerequisites

- Node.js (v18+ recommended)
- Docker & Docker Compose
- Neon/Postgres database credentials

### Installation

```bash
git clone https://github.com/Pragyat-Nikunj/acquisitions.git
cd acquisitions
npm ci
```

### Environment Setup

Copy and configure environment files:

```bash
cp .env.development.example .env.development
cp .env.production.example .env.production
```

Update database and JWT credentials as needed.

### Development

Start the development environment (requires Docker running):

```bash
npm run dev:docker
```

Or run locally:

```bash
npm run dev
```

### Production

Build and run with Docker Compose:

```bash
npm run prod:docker
```

Or manually:

```bash
docker compose -f docker-compose.prod.yml up --build
```

### Database Migrations

Run migrations with Drizzle:

```bash
npm run db:migrate
```

### Testing

Run the test suite:

```bash
npm test
```

## API Endpoints

- `GET /health` — Health check
- `GET /api` — API status
- `POST /api/auth/sign-up` — Register user
- `POST /api/auth/sign-in` — Login
- `POST /api/auth/sign-out` — Logout
- `GET /api/users` — List users (admin)
- `GET /api/users/:id` — Get user by ID
- `PUT /api/users/:id` — Update user
- `DELETE /api/users/:id` — Delete user (admin)

## Docker

- **Dockerfile**: Multi-stage for dev/prod
- **docker-compose.prod.yml**: Production deployment
- **docker-build-and-push.yml**: CI/CD workflow for Docker Hub

