# Express + Passport + JWT Auth Template

Reusable template in Node.js / Express for building authentication backends with Passport and JSON Web Tokens (JWT). Includes user registration, login, protected routes and basic error handling — ready to connect to any frontend.

---

## Features

- User registration and login
- Password hashing (bcrypt)
- JWT-based authentication
- Middleware to protect routes
- MongoDB + Mongoose integration
- Organized structure (config, controllers, middlewares, routes, etc.)
- Environment variable handling with `.env`
- Basic usage examples with curl

---

## Tech Stack

- Runtime: Node.js
- Framework: Express
- Authentication: Passport, passport-jwt
- Tokens: jsonwebtoken
- Database: MongoDB + Mongoose
- Views (optional/demo): EJS (or another engine)
- Env: dotenv

---

## Project Structure

```bash
.
├── public/                 # Static assets (CSS, JS, images)
├── src/
│   ├── config/
│   │   ├── db.js               # Database connection
│   │   └── passport.config.js  # Passport strategies configuration
│   ├── controllers/
│   │   └── user.controller.js  # User logic (register, login, profile, etc.)
│   ├── middlewares/
│   │   ├── auth.js             # JWT middleware & error handling
│   │   └── passportAuth.js     # Passport initialization and helpers
│   ├── models/
│   │   └── User.js             # User model (Mongoose schema)
│   ├── routes/
│   │   ├── user.router.js      # Authentication & user routes
│   │   └── views.router.js     # Example routes for views (optional)
│   └── utils/                  # Utilities (if applicable)
├── views/                      # Templates (optional)
├── .env                        # Environment variables (DO NOT commit)
├── .gitignore
├── index.js                    # Entry point
├── package.json
└── package-lock.json
```

---

## Installation and Running

1. Clone the repository
```bash
git clone https://github.com/Juarex9/express-passport-jwt-auth-template.git
cd express-passport-jwt-auth-template
```

2. Install dependencies
```bash
npm install
```

3. Create the `.env` file in the root (you can use the example below)

4. Run the app
```bash
npm start
# or for development with nodemon (if configured)
npm run dev
```

---

## Example `.env` (use the .env.example already in the repository)
```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/auth_template
JWT_SECRET=your_jwt_secret_here
SESSION_SECRET=your_session_secret_here
```

---

## Middlewares

- auth.js
  - Verifies the JWT from the Authorization header.
  - If the token is valid, attaches the information to `req.user`.
  - Returns 401/403 errors as appropriate.

- passportAuth.js
  - Initializes Passport and configures the JWT strategy (and optionally local).
  - Reusable in routes that require Passport authentication.
