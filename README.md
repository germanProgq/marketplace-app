# marketplace-app

An e-commerce marketplace with a React frontend and a Node.js and Express backend. Users can post product listings, browse and search the catalog, manage a cart, and raise support tickets. Authentication uses JWT, and data is stored in PostgreSQL.

## Tech

**Backend**
- Express, PostgreSQL via `pg`
- `jsonwebtoken` for auth, `bcrypt` for password hashing
- `helmet`, `cors`, `express-rate-limit`, and `express-validator`
- `multer` for image uploads

**Frontend**
- React 18 with Create React App (`react-scripts`)
- `react-router-dom`, `axios`, `framer-motion`, `swiper`

## Setup

You need Node.js and a running PostgreSQL database.

Clone and install both sides:

```sh
git clone https://github.com/germanProgq/marketplace-app
cd marketplace-app

cd backend && npm install
cd ../frontend && npm install
```

### Backend environment

Create a `.env` file in `backend` with your database and token settings:

```
DB_HOST=localhost
DB_PORT=4000
DB_DATABASE_PORT=5432
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PASSWORD=your_db_password
JWT_SECRET_KEY=replace_me
JWT_REFRESH_SECRET_KEY=replace_me
```

`DB_PORT` is the port the API server listens on (it defaults to 4000). The frontend proxies API calls to `http://localhost:4000`.

### Run

```sh
# backend
cd backend && npm start

# frontend (in another terminal)
cd frontend && npm start
```

The frontend runs on `http://localhost:3000`.

## Scripts

Backend:

| Command | What it does |
| --- | --- |
| `npm start` | Run the API server with nodemon |

Frontend:

| Command | What it does |
| --- | --- |
| `npm start` | Start the dev server |
| `npm run build` | Build for production |
| `npm test` | Run tests |

## Layout

```
backend/
  server.js       app entry and setup
  router.js       route wiring
  routes/         cart, catalog, user handlers
  assets/         uploaded and static assets
frontend/
  src/            React app
  public/         static files
```

## License

MIT. See [LICENSE](LICENSE).
