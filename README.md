# Late Show API

The **Late Show API** is a RESTful Flask backend for managing a fictional talk show. It handles Users, Guests, Episodes, and Appearances using a PostgreSQL database, JWT authentication, and Flask-Migrate for schema migrations.

---

## Features

- User registration and JWT-based login
- CRUD operations for Guests, Episodes, and Appearances
- Relationship mapping (e.g., Guests appearing in Episodes)
- Secure password hashing with Werkzeug
- PostgreSQL + Flask-Migrate + SQLAlchemy
- Modular MVC folder structure

---

## Tech Stack

- **Backend**: Python, Flask
- **Database**: PostgreSQL
- **ORM**: SQLAlchemy
- **Migrations**: Flask-Migrate (Alembic)
- **Auth**: Flask-JWT-Extended
- **Dev Tools**: Postman, .env, pipenv/venv

---

## Project Structure
```bash
late-show-api-challenge/
├── server/
│ ├── app.py
│ ├── config.py
│ ├── seed.py
│ ├── models/
│ │ ├── init.py
│ │ ├── user.py
│ │ ├── guest.py
│ │ ├── episode.py
│ │ └── appearance.py
│ └── controllers/
│ ├── auth_controller.py
│ ├── guest_controller.py
│ ├── episode_controller.py
│ └── appearance_controller.py
├── migrations/
├── .env
└── Pipfile / requirements.txt

```
---

## Setup Instructions

 1. Clone the Repository

`git clone https://github.com/BILLADAMS-arch/two-late-show-API`
`cd late-show-api`

 2. Create a virtual Environment
`python3 -m venv venv`
`source venv/bin/activate  # or source venv/bin/activate.fish`

 3. Install Dependencies
`pip install -r requirements.txt`

 4. Set Environment Variables
`FLASK_APP=server/app.py`
`FLASK_ENV=development`
`DATABASE_URL=postgresql://username:password@localhost:5432/late_show_db`
`JWT_SECRET_KEY=your_secret_key`

 5. Run Migrations and Seed
`export FLASK_APP=server/app.py`
`export PYTHONPATH=.`
`flask db upgrade`
`python3 server/seed.py `
Note: seed.py populates the database with sample users, guests, episodes, and appearances for testing and development purposes.

## API Routes

### 🔐 Users
| Method | Endpoint        | Description       |
|--------|-----------------|-------------------|
| POST   | `/register`     | Register a user   |
| POST   | `/login`        | Login and get JWT |

### 🎤 Guests
| Method | Endpoint       | Description         |
|--------|----------------|---------------------|
| GET    | `/guests`      | Get all guests      |
| POST   | `/guests`      | Add a new guest     |
| DELETE | `/guests/<id>` | Delete a guest      |

### 🎬 Episodes
| Method | Endpoint         | Description           |
|--------|------------------|-----------------------|
| GET    | `/episodes`      | Get all episodes      |
| POST   | `/episodes`      | Add a new episode     |
| DELETE | `/episodes/<id>` | Delete an episode     |

### 👥 Appearances
| Method | Endpoint             | Description                |
|--------|----------------------|----------------------------|
| GET    | `/appearances`       | Get all appearances        |
| POST   | `/appearances`       | Create an appearance       |
| DELETE | `/appearances/<id>`  | Delete an appearance       |

## Testing Tools
Use Postman or cURL to test API endpoints.
Include JWT tokens in the Authorization header as Bearer <token> when accessing protected routes.

