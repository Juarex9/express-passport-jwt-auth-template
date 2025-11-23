# Express + Passport + JWT Auth Template

A reusable **Node.js / Express** starter template for building authentication backends with **Passport** and **JSON Web Tokens (JWT)**.  
Includes user registration, login, protected routes and basic error handling, ready to plug into any frontend.

---

## Features

- User registration and login
- Password hashing
- JWT-based authentication
- Protected routes via middleware
- MongoDB + Mongoose integration
- Organized project structure (config, controllers, middlewares, routes, etc.)
- Environment variables support with `.env`

---

## Tech Stack

- **Runtime:** Node.js
- **Framework:** Express
- **Auth:** Passport, Passport JWT
- **Tokens:** JSON Web Token (JWT)
- **Database:** MongoDB + Mongoose
- **Views (optional/demo):** EJS (or similar)
- **Env management:** dotenv

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
│   │   ├── auth.js             # JWT auth middleware & error handling
│   │   └── passportAuth.js     # Passport initialization / helpers
│   ├── models/
│   │   └── User.js             # User model (Mongoose schema)
│   ├── routes/
│   │   ├── user.router.js      # Auth & user-related routes
│   │   └── views.router.js     # Example routes for views (optional)
│   └── utils/                  # Utility functions (if needed)
├── views/                      # View templates (optional)
├── .env                        # Environment variables (NOT committed)
├── .gitignore
├── index.js                    # Application entry point
├── package.json
└── package-lock.json


Setup & Installation
1. Clone the repository
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
2. Install dependencies
npm install
3. Create your .env file
Create a .env file in the project root based on the example below:
PORT=3000
MONGO_URI=mongodb://localhost:27017/auth_template
JWT_SECRET=changeme
SESSION_SECRET=changeme
4. Run the application
npm start
# or, if you have a dev script with nodemon:
npm run dev
Middlewares
auth.js
- Verifies the JWT from the Authorization header.
- Attaches the decoded user information to req.user.
- Returns appropriate error codes if the token is missing or invalid.
passportAuth.js
- Sets up Passport initialization.
- Configures JWT strategy (and optionally a local strategy).
- Can be reused in any route that requires Passport authentication.
