# SkillBoard – Job & Applicant Tracking

SkillBoard centralizes hiring workflows for student communities and small teams. It includes a **Node/Express/Prisma** backend with role-based JWT auth and a **React + Tailwind** frontend built around a clean black-and-white aesthetic.

## Tech Stack
- Backend: Node.js, Express, Prisma ORM, MySQL (PlanetScale/TiDB compatible)
- Frontend: React (Vite), React Router, Axios, TailwindCSS
- Auth: JWT access tokens, bcrypt password hashing

## Getting Started

### 1. Clone & install
```bash
git clone <repo>
cd capstone-2ndyear

# backend
cd backend
npm install

# frontend
cd ../frontend
npm install
```

### 2. Environment variables
Copy `.env.example` in `backend/` to `.env` and update:

```
DATABASE_URL="mysql://USER:PASSWORD@HOST:PORT/DATABASE"
JWT_SECRET="super-secret"
JWT_EXPIRES_IN="1d"
PORT=5000
CLIENT_URL="http://localhost:5173"
```

For local development you can point Prisma to PlanetScale, TiDB Cloud, Railway MySQL, etc. Run `npx prisma migrate dev` after updating the schema.

### 3. Run the apps

```bash
# backend
cd backend
npm run dev

# frontend (new terminal)
cd frontend
npm run dev
```

The frontend expects the API at `http://localhost:5000/api`. Change `VITE_API_BASE_URL` in `frontend/.env` if you deploy elsewhere.

## API Highlights
- `POST /api/auth/signup` – register applicants or employers
- `POST /api/auth/login` – issue JWT token
- `GET /api/jobs` – list jobs with search, filters, pagination
- `POST /api/jobs` – employers/admins create jobs
- `PUT /api/jobs/:id`, `DELETE /api/jobs/:id`
- `POST /api/jobs/:id/applications` – applicants submit
- `GET /api/employer/applications`, `PUT /api/applications/:id/status`

## Frontend Pages
- Landing page with hero + stats
- Job board with filters & noir cards
- Job detail + application form
- Auth (login/signup) with role switcher
- Role-aware dashboard for applicants, employers, and admins

## Deployment
- **Frontend** → Vercel / Netlify
- **Backend** → Render / Railway / Fly
- **Database** → PlanetScale / TiDB Cloud

Set the appropriate environment variables in each platform (API URLs, database credentials, JWT secret). Update `CLIENT_URL` so CORS allows your hosted frontend.
