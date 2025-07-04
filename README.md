# GeoChat Backend

REST API for a geolocated chat app.
- Stack: FastAPI (async), SQLAlchemy async, PostgreSQL, JWT auth, DDD structure.
- Features: User auth, geo-channels (world/country/region/city), messages.

## Local setup

```bash
# Install dependencies (if not already done)
uv sync

# Run the app (hot reload)
uvicorn app.main:app --reload

# Run migrations
alembic upgrade head

## Project structure

```
app/
├── api/               # Routers and endpoints
├── core/              # App settings, logging, security utils
├── db/                # DB connection, Alembic, base class
├── domains/           # DDD: entities, repositories, services SQLAlchemy models
    ├── user/
    ├── geo_channel/
    ├── message/
├── enums/             
├── schemas/           # Shared Pydantic schemas
├── services/          # Shared services (auth, security, etc.)
main.py                # FastAPI app instance

## **.env.example**

```dotenv
POSTGRES_HOST=localhost
POSTGRES_PORT=5432
POSTGRES_DB=geochat
POSTGRES_USER=geochat
POSTGRES_PASSWORD=geochat
JWT_SECRET=changeme


