# SpendWise - Backend API

SpendWise is a backend application designed to help beginner developers learn how to build secure REST APIs using Node.js, Express, MongoDB, and JWT authentication. It provides a simple and practical backend project to learn CRUD operations and understand how protected routes work using middleware.

## 🚀 Features
* **User Authentication:** User Registration and Login with JWT authentication.
* **Data Management:** CRUD operations (Create, Read, Update, Delete) on user data.
* **Security:** JWT middleware is used to protect routes, ensuring each user can access only their own data.
* **Database Integration:** System stores user and record data in MongoDB using Mongoose.

## 🛠️ Technology Stack
* **Runtime:** Node.js
* **Framework:** Express.js
* **Database:** MongoDB & Mongoose
* **Security:** JSON Web Token (JWT) & bcryptjs
* **Configuration:** dotenv, cors

## 📁 Project Structure
The project uses a clean folder structure to teach best practices:

    spendwise/
    ├── config/           # Database connection setup
    ├── controllers/      # Business logic for auth and CRUD
    ├── middleware/       # JWT verification and request protection
    ├── models/           # Mongoose schemas for User and Transaction
    ├── routes/           # API endpoints for auth and CRUD operations
    ├── .env              # Environment variables
    ├── server.js         # Entry point of the application
    └── package.json      # Project dependencies and scripts


## ⚙️ Getting Started

### Prerequisites
Make sure you have the following installed on your machine:
* Node.js
* MongoDB (Local or Atlas)
* Git

### Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/balafromtn/NM-Project-Spendwise.git
   cd NM-Project-Spendwise
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure Environment Variables:**
   Create a `.env` file in the root directory and add your specific credentials:
   ```text
   PORT=5000
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_secret_jwt_key
   ```

4. **Start the server:**
   ```bash
   npm run dev
   ```
   The server will start on `http://localhost:5000` and you should see a "MongoDB Connected" message in your terminal.

## 🔗 API Endpoints

You can easily test these APIs using Postman or Thunder Client.

### Authentication (Public)
| Method | Endpoint | Description | Body Required |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/auth/register` | Register a new user | `name`, `email`, `password` |
| `POST` | `/api/auth/login` | Login and get JWT token | `email`, `password` |

### Transactions (Protected)
*Note: All protected routes require a valid JWT token in the `Authorization` header as a `Bearer Token`.*

| Method | Endpoint | Description | Body Required |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/transactions` | Create a new record | `amount`, `type`, `category`, `note` |
| `GET` | `/api/transactions` | Get all records for the logged-in user | None |
| `PUT` | `/api/transactions/:id` | Update a specific record | fields to update |
| `DELETE` | `/api/transactions/:id` | Delete a specific record | None |

## 👨‍💻 Author
**Balaji**
* GitHub: [@balafromtn](https://github.com/balafromtn)
