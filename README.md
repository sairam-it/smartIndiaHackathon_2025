# SmartIndiaHackathon_2025 — Incredible India Travel Companion

## Description

Incredible India is a full-stack web application built during Smart India Hackathon 2025 to help travellers discover destinations, plan trips, book local guides, chat with support, and keep travel safety checks. The site offers curated cultural and tourist destinations, itinerary planning, wishlist management, hotel and experience browsing, guide bookings, and basic safety monitoring features.

## Key Features

- Browse curated destinations, experiences, and hotels
- Create and manage trip plans and itineraries
- Add/remove items to a wishlist
- Register and sign in as a tourist or a guide
- Book guides and manage bookings
- In-app chat functionality for support/communication
- Safety checks and alert scheduling for active trips
- Guided flows for cultural destination details and bookings

## Tech Stack

- Frontend: React (TypeScript) with Vite and Tailwind CSS
- Backend: Node.js with Express
- Database: MongoDB with Mongoose ODM
- Auth: JSON Web Tokens (JWT)
- Dev tools: Nodemon (backend), Vite dev server (frontend)
- HTTP client: Axios (frontend)

These technologies are confirmed from the project files `frontend/package.json` and `backend/package.json`.

## Repository Structure (high level)

- backend/: API server (Express, Mongoose)
  - src/index.js — server entry
  - src/routes/ — API routes (auth, bookings, trip plans, chat, wishlist, safety, plans)
  - src/models/ — Mongoose models (User, TripPlan, Booking, Wishlist, etc.)
  - guide/: extra guide-related controllers & routes
- frontend/: React + TypeScript client (Vite)
  - src/: React components, contexts, pages
  - index.html, vite.config.ts, tailwind.config.js

## API Endpoints (overview)

The backend registers these top-level routes (see `backend/src/index.js`):

- `POST /api/auth` — authentication routes (register, login)
- `GET/POST /api/wishlist` — wishlist management
- `GET/POST /api/tripplans` — create and manage trip plans
- `POST /api/chat` — chat interactions/support
- `GET/POST /api/bookings` — booking guides and trips
- `GET/POST /api/plans` — itinerary / plans management
- `POST /api/safety` — safety checks and alerts
- `GET/POST /api/guide` — guide profiles and guide bookings

Refer to the route files in `backend/src/routes/` for exact request shapes and additional endpoints.

## Environment Variables

Create a `.env` file in the `backend/` folder with at least the following variables:

- `MONGO_URI` — MongoDB connection string
- `JWT_SECRET` — secret for signing JWT tokens
- `PORT` — (optional) port for the backend server (default 5000)

There may be other optional keys used by certain controllers (e.g., mailer credentials) — check `backend/src` and `guide/` controller files for details.

## Local Setup — Backend

Prerequisites: Node.js (v16+ recommended), MongoDB (local or Atlas)

1. Open a terminal and install dependencies:

```bash
cd backend
npm install
```

2. Add `.env` with `MONGO_URI` and `JWT_SECRET`.

3. Start server (development):

```bash
npm run start
```

The server runs by default on `http://localhost:5000` unless you set `PORT` in `.env`.

## Local Setup — Frontend

Prerequisites: Node.js

1. Install dependencies and start dev server:

```bash
cd frontend
npm install
npm run dev
```

2. The Vite dev server will print the local URL (usually `http://localhost:5173`).

To connect frontend to the local backend, update any API base URL configuration or environment usage in the frontend code to point to `http://localhost:5000/api`.

## Development Tips

- Backend logging includes request logging in `backend/src/index.js`.
- The backend uses a lightweight scheduler to run periodic safety checks (see `tripPlanController` import in `src/index.js`).
- Frontend uses Tailwind CSS utilities and includes a `@tailwindcss/typography` plugin.

## Contributing

Contributions are welcome. For quick fixes or features:

1. Fork the repository and create a feature branch.
2. Add tests where appropriate and verify the app runs locally (both frontend and backend).
3. Open a pull request with a clear description of the change.

## License

This repository does not include an explicit open-source license file. Add a `LICENSE` file if you intend to make the project open source.

---

If you want, I can also:

- Add more detailed developer notes for specific endpoints.
- Create a Postman collection or OpenAPI spec from the routes.
- Add sample `.env.example` and start scripts to simplify setup.

File created: README.md
