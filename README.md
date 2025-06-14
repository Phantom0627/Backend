# ⚡ FastAPI Backend

A high-performance FastAPI backend with integrated authentication, database support, and edge function hooks — designed to be modular, scalable, and production-ready.

## 🚀 Features

- ✅ **FastAPI**: Lightweight and blazing-fast API framework.
- 🔒 **Authentication System**:
  - JWT-based authentication
  - User registration and login
  - Password hashing
- 🗃️ **Database Integration**:
  - SQLAlchemy or Tortoise ORM
  - PostgreSQL or SQLite support
  - Async database interactions
- 🌐 **Edge Functions** (Pluggable):
  - Easily extend backend functionality via custom edge functions
- 📦 Modular project structure for maintainability

---

## 📁 Project Structure

```

fastapi-backend/
│
├── app/
│   ├── main.py              # Entry point
│   ├── models/              # Database models
│   ├── schemas/             # Pydantic schemas
│   ├── api/                 # Route definitions
│   ├── core/                # Auth, config, utils
│   ├── services/            # Business logic & edge functions
│   └── db/                  # DB session and init
│
├── .env                     # Environment variables
├── requirements.txt         # Python dependencies
└── README.md                # You're here

```

---

## 🛠️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/fastapi-backend.git
cd fastapi-backend
```

### 2. Create and Activate Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Set Environment Variables

Create a `.env` file in the root directory:

```env
DATABASE_URL=sqlite:///./app.db  # or your PostgreSQL URI
SECRET_KEY=your-secret-key
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
```

### 5. Run the Server

```bash
uvicorn app.main:app --reload
```

Visit [http://localhost:8000/docs](http://localhost:8000/docs) for the Swagger API documentation.

---

## 🧩 Edge Function Support

You can add custom "edge functions" inside `app/services/edge/`. The system will automatically detect and route them based on your implementation.

Example placeholder:

```python
# app/services/edge/example.py

def run_edge_function(payload):
    # Your logic here
    return {"result": "This is a custom edge function response"}
```

---

## 🔐 Authentication Endpoints

- `POST /auth/register` – Create a new user
- `POST /auth/login` – Get access token
- `GET /users/me` – Get current user info (protected)

---

## 🗃️ Database

Using **SQLAlchemy** (or you can switch to Tortoise/another ORM).

To initialize the database (for SQLite/PostgreSQL):

```bash
alembic upgrade head  # If using Alembic migrations
```

---

## 📌 To-Do

- [ ]Make the app lmao

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙌 Contributing

Pull requests are welcome! For major changes, open an issue first to discuss what you’d like to change.
