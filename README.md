# Flex Office API

Express + MongoDB backend for the booking and building-admin screens in `frontend/`.

## Run locally

1. Copy `.env.example` to `.env` and set `MONGODB_URI` and `JWT_SECRET`.
2. Install dependencies with `npm install`.
3. Seed demo spaces and the admin account with `npm run seed`.
4. Start the API with `npm run dev` (or `npm start`).

The API runs on `http://localhost:5000` by default. Health check: `GET /api/health`.

## Endpoints

- `POST /api/auth/signup`, `POST /api/auth/signin`, `GET /api/auth/me`
- `GET /api/resources?type=desks&search=window`
- `GET /api/resources/:id/children` to view spaces inside a floor, room, or parking area
- `POST /api/resources`, `PATCH /api/resources/:id` (admin)
- `GET /api/bookings/mine`, `GET /api/bookings/availability?date=YYYY-MM-DD`
- `POST /api/bookings`, `PATCH /api/bookings/:id/cancel`
- `GET /api/admin/dashboard` (admin)

Send authenticated requests with `Authorization: Bearer <token>`.

When creating a nested space, include `parentId`. Parking spaces may also include
`vehicleType`: `Two-wheeler`, `Three-wheeler`, or `Four-wheeler`.
