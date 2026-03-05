# SpendWise Backend API

SpendWise is a simple backend learning project built using Node.js, Express, and MongoDB. It allows users to register, login using JWT authentication, and perform basic CRUD operations on their own financial transaction records.

## 🚀 Technologies Used
* **Node.js & Express.js:** Server and API framework
* **MongoDB & Mongoose:** Database and Object Data Modeling (ODM)
* **JWT (JSON Web Token):** Secure user authentication
* **Bcrypt.js:** Password hashing

## 📁 Project Structure
```text
spendwise/
├── config/           # Database connection setup
├── controllers/      # Business logic for routes
├── middleware/       # JWT authentication protection
├── models/           # Mongoose schemas (User, Transaction)
├── routes/           # Express API endpoints
├── .env              # Environment variables (ignored in git)
├── server.js         # Entry point of the application
└── package.json      # Project dependencies
⚙️ Setup and Installation
Clone the repository (if using Git):

Bash
git clone <your-repo-url>
cd spendwise
Install dependencies:

Bash
npm install
Set up Environment Variables:
Create a .env file in the root directory and add the following:

Plaintext
PORT=5000
MONGO_URI=your_mongodb_atlas_connection_string
JWT_SECRET=your_super_secret_jwt_key
Run the server:

Bash
npm run dev
The server should start on http://localhost:5000 and connect to MongoDB.

🔗 API Endpoints
Authentication APIs (Public)
Register User: POST /api/auth/register

Body: { "name": "John", "email": "john@test.com", "password": "password123" }

Login User: POST /api/auth/login

Body: { "email": "john@test.com", "password": "password123" }

Returns a JWT Token to be used in protected routes.

Transaction APIs (Protected - Requires JWT Token)
Add the token to your request headers as: Authorization: Bearer <your_token>

Create Record: POST /api/transactions

Body: { "amount": 500, "type": "expense", "category": "Food", "note": "Lunch" }

Get All Records: GET /api/transactions

Update Record: PUT /api/transactions/:id

Delete Record: DELETE /api/transactions/:id