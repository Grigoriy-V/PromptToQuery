# Text2DB

A service that converts natural language queries into SQL, executes them on a database, and returns results.

---

## 🚀 Features

- **SQL Generation:** Transform user prompts into SQL queries using LLM (OpenAI GPT-3.5/4).  
- **Query Execution:** Run SQL against SQLite or PostgreSQL via SQLAlchemy.  
- **Logging:** Store user prompt, generated SQL, execution timestamp, and results in the `query_logs` table.  
- **Caching:** Speed up repeated queries using Redis with aiocache.  
- **Authentication:** Secure API endpoints with JWT tokens (fastapi-jwt-auth).  
- **Frontend UI:** React app to input prompts, view SQL, and display results.  
- **Monitoring:** Expose Prometheus metrics via `prometheus-fastapi-instrumentator`.  
- **Containerization:** Docker & Docker Compose for easy deployment.  
- **CI/CD:** GitHub Actions for automated testing.

---

## 🧰 Tech Stack

- **Backend:** FastAPI, Uvicorn, SQLAlchemy, Databases, Alembic  
- **LLM:** OpenAI Python SDK (GPT-3.5/4)  
- **Cache:** Redis, aiocache  
- **Auth:** fastapi-jwt-auth  
- **Frontend:** React, React Router, Axios  
- **DevOps:** Docker, Docker Compose, GitHub Actions  

---

## 📦 Installation

```bash
bash init_llm_sql.sh       # Set up project structure
cd llm-sql-project         # Enter project root
pip install -r requirements.txt
```

---

## ⚙️ Configuration

Copy and edit the environment file:

```bash
cp config/.env.example .env
```

Edit `.env` with your credentials and settings:

```ini
# OpenAI API
OPENAI_API_KEY=your_openai_api_key
LLM_MODEL=gpt-3.5-turbo

# Database URL (SQLite or PostgreSQL)
DATABASE_URL=sqlite:///./db/app.db

# Redis
REDIS_URL=redis://localhost:6379/0

# JWT Authentication
JWT_SECRET_KEY=your_jwt_secret

# API Host and Port
API_HOST=0.0.0.0
API_PORT=8000
```

---

## 🚀 Running Locally

### Backend API

```bash
uvicorn src.api.main:app --reload
```

### Frontend UI

```bash
cd frontend
npm install
npm start
```

Visit [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🐳 Docker Deployment

```bash
cd docker
docker-compose up --build
```

---

## 🔄 Database Migrations

```bash
alembic upgrade head
```

---

## ✅ Running Tests

```bash
pytest -q
```

