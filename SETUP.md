# 🚀 Hackathon Management Website - Setup Guide

This is a complete MERN stack hackathon management platform with an attractive, modern UI built with React and Tailwind CSS.

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v14 or higher)
- **MongoDB** (local installation or MongoDB Atlas)
- **npm** or **yarn**

## 🛠️ Installation & Setup

### 1. Clone the Repository
```bash
git clone <your-repo-url>
cd hackathon-website
```

### 2. Backend Setup

Navigate to the backend directory and install dependencies:
```bash
cd backend
npm install
```

Create a `.env` file in the backend directory:
```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/hackathon_db
JWT_SECRET=your_super_secret_jwt_key_here_change_this_in_production
```

**Important:** Replace `your_super_secret_jwt_key_here_change_this_in_production` with a strong, random secret key for production use.

### 3. Frontend Setup

Navigate to the frontend directory and install dependencies:
```bash
cd ../frontend
npm install
```

### 4. Database Setup

Make sure MongoDB is running on your system:
- **Local MongoDB:** Start your MongoDB service
- **MongoDB Atlas:** Use your connection string in the `.env` file

## 🚀 Running the Application

### Start the Backend Server
```bash
cd backend
npm run dev
```
The backend will run on `http://localhost:5000`

### Start the Frontend Development Server
```bash
cd frontend
npm start
```
The frontend will run on `http://localhost:3000`

## 📱 Features

### ✅ Implemented Features
- **User Authentication** (Signup/Login with JWT)
- **Responsive Design** with Tailwind CSS
- **Team Registration** (Solo, Duo, Team options)
- **User Profile Management**
- **Problem Statements Display**
- **Sponsors Information**
- **About Us Page**
- **Protected Routes**
- **Modern UI/UX Design**

### 🔧 Backend API Endpoints
- `POST /api/auth/signup` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile
- `PUT /api/users/change-password` - Change password
- `POST /api/teams/register` - Register team
- `GET /api/teams` - Get all teams
- `GET /api/teams/my-team` - Get user's team
- `GET /api/teams/problem-statements` - Get problem statements

## 🎨 Design Features

- **Modern Gradient Backgrounds**
- **Responsive Navigation Bar**
- **Card-based Layout**
- **Smooth Animations**
- **Professional Color Scheme**
- **Mobile-First Design**

## 📁 Project Structure

```
hackathon-website/
├── backend/
│   ├── config/
│   │   └── db.js
│   ├── models/
│   │   ├── User.js
│   │   └── Team.js
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── userRoutes.js
│   │   └── teamRoutes.js
│   ├── middleware/
│   │   └── authMiddleware.js
│   ├── server.js
│   ├── package.json
│   └── .env
└── frontend/
    ├── src/
    │   ├── components/
    │   │   ├── Navbar.jsx
    │   │   └── ProtectedRoute.jsx
    │   ├── contexts/
    │   │   └── AuthContext.jsx
    │   ├── pages/
    │   │   ├── Home.jsx
    │   │   ├── Login.jsx
    │   │   ├── Signup.jsx
    │   │   ├── TeamRegister.jsx
    │   │   ├── Profile.jsx
    │   │   ├── About.jsx
    │   │   ├── ProblemStatements.jsx
    │   │   └── Sponsors.jsx
    │   ├── api/
    │   │   └── axios.js
    │   ├── App.jsx
    │   ├── index.jsx
    │   └── index.css
    ├── public/
    │   └── index.html
    ├── tailwind.config.js
    ├── postcss.config.js
    └── package.json
```

## 🔐 Security Features

- **JWT Authentication**
- **Password Hashing** with bcrypt
- **Protected Routes**
- **Input Validation**
- **CORS Configuration**

## 🎯 Usage

1. **Sign Up:** Create a new account with registration number, email, and password
2. **Login:** Access your account with email and password
3. **Register Team:** Create a team (Solo, Duo, or Team with 3-5 members)
4. **View Problem Statements:** Browse available challenges
5. **Manage Profile:** Update personal information and change password
6. **Explore Sponsors:** Learn about our amazing sponsors

## 🚀 Deployment

### Backend Deployment
- Deploy to platforms like **Heroku**, **Railway**, or **Render**
- Set environment variables in your hosting platform
- Use **MongoDB Atlas** for production database

### Frontend Deployment
- Deploy to **Vercel**, **Netlify**, or **GitHub Pages**
- Update API URL in production environment

## 🛠️ Customization

### Adding New Problem Statements
Edit `backend/routes/teamRoutes.js` and update the `problemStatements` array.

### Styling Changes
Modify `frontend/src/index.css` and `frontend/tailwind.config.js` for custom styling.

### Adding New Features
Follow the existing patterns in the codebase for consistency.

## 📞 Support

For any issues or questions:
- Check the console for error messages
- Ensure MongoDB is running
- Verify environment variables are set correctly
- Check network connectivity between frontend and backend

## 🎉 You're All Set!

Your hackathon management platform is now ready to use! The application provides a complete solution for managing hackathon registrations with a beautiful, modern interface.

**Happy Coding! 🚀**
