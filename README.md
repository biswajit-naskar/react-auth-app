# React Authentication App

## 🚀 Project Overview
A complete React application with JWT authentication, role-based authorization, and protected routes. This project demonstrates secure user authentication, session management, and responsive UI design.

## 📋 Features

### Backend Features
- User registration with password hashing (bcrypt)
- User login with JWT token generation
- HTTP-only cookies for secure token storage
- Role-based access control (User/Admin)
- Protected API routes
- Password validation and sanitization
- MongoDB database integration

### Frontend Features
- React functional components with hooks
- Form validation and error handling
- Protected routes with React Router
- Role-based UI rendering
- Toast notifications for user feedback
- Responsive design with custom CSS

## 🛠️ Technologies Used

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - ODM for MongoDB
- **JWT** - JSON Web Tokens for authentication
- **bcryptjs** - Password hashing
- **Cookie-parser** - Cookie handling
- **CORS** - Cross-Origin Resource Sharing

### Frontend
- **React.js** - UI library
- **React Router** - Navigation and routing
- **Axios** - HTTP client
- **CSS3** - Custom styling

## 📂 Project Structure

react-auth-app/
│
├── task1-react-frontend/ # React Frontend
│ ├── src/
│ │ ├── components/ # React components
│ │ │ ├── Login.js # Login component
│ │ │ └── Signup.js # Signup component
│ │ ├── services/ # API services
│ │ │ └── api.js # Axios configuration
│ │ ├── App.js # Main component
│ │ └── App.css # Global styles
│ ├── public/ # Public assets
│ └── package.json # Dependencies
│
├── task2-auth-backend/ # Auth Backend
│ ├── models/ # Database models
│ │ └── user.model.js # User schema
│ ├── routes/ # API routes
│ │ ├── auth.routes.js # Auth routes
│ │ └── user.routes.js # User routes
│ ├── controllers/ # Business logic
│ │ └── auth.controller.js # Auth controller
│ ├── middleware/ # Custom middleware
│ │ └── auth.middleware.js # Auth middleware
│ ├── server.js # Entry point
│ ├── .env # Environment variables
│ └── package.json # Dependencies
│
└── README.md # Project documentation

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud)
- npm or yarn package manager

### Environment Variables

Create a `.env` file in the `task2-auth-backend/` folder with:
PORT=5001
JWT_SECRET=your_super_secret_key_here
NODE_ENV=development

| Variable | Description | Default |
|----------|-------------|---------|
| `PORT` | Server port number | `5001` |
| `JWT_SECRET` | Secret key for JWT signing | Required |
| `NODE_ENV` | Environment mode | `development` |

### Backend Setup

1. **Navigate to backend folder**

cd task2-auth-backend

3. **Install dependencies**
   
npm install

3. **Start development server**

npm run dev

### Frontend Setup

1. **Navigate to frontend folder**

cd task1-react-frontend

2. **Install dependencies**

npm install

3. **Start React development server**

npm start

## 🔗 API Endpoints

### Base URL

http://localhost:5001/api

### Auth Routes

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/auth/signup` | Register a new user | ❌ |
| POST | `/auth/login` | Login user | ❌ |
| POST | `/auth/logout` | Logout user | ✅ |
| GET | `/auth/me` | Get current user | ✅ |

### Protected Routes

| Method | Endpoint | Description | Role Required |
|--------|----------|-------------|---------------|
| GET | `/users/profile` | User profile | User |
| GET | `/users/admin` | Admin dashboard | Admin |

## 🔐 Authentication Flow

1. **Signup** → User creates account → Password is hashed → User is created
2. **Login** → User logs in → JWT token is generated → Token stored in HTTP-only cookie
3. **Protected Routes** → Token is verified → Access granted based on role
4. **Logout** → Cookie is cleared → Session ends

## 📸 Screenshots

### Login Page
┌──────────────────────────────────────┐
│ 🔐 Login │
│ [Email Address ___________] │
│ [Password ____________] │
│ [ Login ] │
│ Don't have an account? Signup │
└──────────────────────────────────────┘

### Dashboard (After Login)
┌──────────────────────────────────────┐
│ 🌟 React Auth App Welcome, User│
│ │
│ Dashboard │
│ You are logged in as: user@example │
│ Role: user │
│ │
│ User Info │
│ { │
│ "id": "...", │
│ "name": "John Doe", │
│ "email": "user@example.com", │
│ "role": "user" │
│ } │
└──────────────────────────────────────┘

## 🎯 Key Features Demonstrated

| Feature | Description |
|---------|-------------|
| **JWT Authentication** | Secure token-based authentication |
| **Role-Based Access** | Different permissions for User/Admin |
| **HTTP-Only Cookies** | Secure token storage |
| **Protected Routes** | Routes that require authentication |
| **Password Hashing** | Secure password storage with bcrypt |
| **Form Validation** | Input validation on frontend and backend |

## 🧪 Testing

### Using Postman/Thunder Client

1. **Signup:** POST `/api/auth/signup`
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "123456",
  "role": "user"
}
Login: POST /api/auth/login

{
  "email": "john@example.com",
  "password": "123456"
}

Get Current User: GET /api/auth/me (requires authentication)

Logout: POST /api/auth/logout (requires authentication)

Testing the Frontend

Go to http://localhost:3000

Click "Signup" to create a new account

Login with your credentials

View your dashboard

Click "Logout" to end session

📦 Deployment

Backend Deployment (Render/Heroku)

# Add to package.json
"scripts": {
  "start": "node server.js"
}

# Set environment variables:
# PORT, JWT_SECRET, MONGODB_URI

Frontend Deployment (Vercel/Netlify)

npm run build
# Upload build folder to Vercel/Netlify
