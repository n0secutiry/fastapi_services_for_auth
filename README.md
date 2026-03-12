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
DATABASE_URL=postgresql+asyncpg://postgres:postgres@db:5432/fastapi_db
SECRET_KEY=SECRET_KEY
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
REFRESH_TOKEN_EXPIRE_MINUTES=10080

POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_DB=fastapi_db

TEST_DATABASE_URL=postgresql+asyncpg://postgres:postgres@db:5432/fastapi_test_db

ENV_MODE=local
```
```
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
