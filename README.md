# Skillshare Backend

Backend API for a skill/knowledge sharing platform where users can register, log in, and interact with skills/courses through a RESTful API.

---

## 1. Tech stack

This project is built using the following technologies:

- **Node.js** – JavaScript runtime for the backend server  
- **Express.js** – Web framework to build REST APIs  
- **MongoDB** – NoSQL database to store users and other data  
- **Mongoose** – ODM to define schemas and interact with MongoDB  
- **JWT (JSON Web Tokens)** – For stateless authentication  
- **bcrypt** – For securely hashing user passwords  

---

## 2. Main features

The backend currently focuses on core backend concepts and features:

- **User authentication**
  - User signup and login
  - Password hashing with bcrypt
  - JWT token generation on login
  - Auth middleware to protect routes

- **CRUD operations**
  - Create, read, update, delete operations for main resources (for example: users / courses / skills depending on your models)
  - Uses Mongoose models and controllers for clean separation

- **MongoDB integration**
  - Connection to MongoDB using Mongoose
  - Schemas and models to structure data

- **Middleware usage**
  - Authentication middleware to verify JWT
  - Other Express middlewares like `express.json()` for parsing JSON requests

---

## 3. Project structure (high level)

> Adjust this if your folder names differ, but this represents the typical structure you are using.

```bash
skillshare-backend/
├── src/
│   ├── config/
│   │   └── database.js      # MongoDB connection setup
│   ├── models/              # Mongoose models (User, etc.)
│   ├── controllers/         # Request handlers / business logic
│   ├── routes/              # Express route definitions (auth, main resources)
│   ├── middlewares/         # Auth middleware and others
│   └── utils/               # Helper functions (if any)
├── app.js                   # Express app configuration
├── server.js                # Server bootstrap (listening on PORT)
├── package.json             # Dependencies and scripts
└── README.md
4. Installation and setup
Prerequisites
Make sure you have:

Node.js installed (LTS version recommended)

MongoDB instance (local or MongoDB Atlas)

npm or yarn

Steps
Clone the repository

bash
git clone https://github.com/Manojuio/skillshare-backend.git
cd skillshare-backend
Install dependencies

bash
npm install
Environment variables

Create a .env file in the root of the project with at least:

text
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_here
NODE_ENV=development
PORT – Port on which the server will run

MONGO_URI – Connection string for your MongoDB database

JWT_SECRET – Secret key for signing JWT tokens

Run the server

Development (with nodemon if configured):

bash
npm run dev
or normal start:

bash
npm start
The backend will be available at:

text
http://localhost:5000
5. API overview (generic)
Replace names with your actual routes, but this describes what you are doing.

Auth routes
POST /api/auth/signup

Register a new user

Validates input, hashes password, stores user in MongoDB

POST /api/auth/login

Login user with email and password

Verifies password using bcrypt

Returns a signed JWT on success

Protected routes
All protected routes use an auth middleware that:

Reads the token from Authorization: Bearer <token> header

Verifies the JWT using JWT_SECRET

Attaches the user info to req.user if valid

Example generic protected route:

GET /api/some-resource – Only accessible if JWT is valid

6. Scripts (from package.json)
Common scripts you are using:

npm start – Start the server in production mode

npm run dev – Start the server in development mode (typically with nodemon)

7. Purpose
This backend is mainly built for:

Practicing Node.js + Express + MongoDB

Understanding authentication with JWT

Learning project structure (models, controllers, routes, middlewares)

Building a solid portfolio project for internships and job applications

text
