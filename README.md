## FastAPI Modular API Service

An asynchronous REST API service featuring JWT authentication with Redis-based session invalidation, role-based access control (Admin/User), and user soft-deletion.

## Tech Stack
Framework: FastAPI (Python 3.11+)

Database: PostgreSQL, SQLAlchemy 2.0 (asyncpg), Alembic

Cache & Sessions: Redis, aiocache

Security: JWT, pwdlib (bcrypt)

Infrastructure: Docker, Docker Compose

Testing: Pytest, pytest-asyncio, Coverage

## How to Run

Create a .env file in the root directory:

```bash
cp .env.example .env
```
Run server
```bash
docker compose up --build -d
```
Apply database migrations:
```bash
docker compose exec web alembic upgrade head
```
The API is now running at: http://localhost:8000

Swagger UI documentation: http://localhost:8000/docs

## Testing
To run the test suite:

```bash
docker compose exec web python -m pytest -v
```
