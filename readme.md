# 🧠 Hackathon Management Website (MERN Stack)
and the layout should be eye catchy and Attractive+simple
A full-stack web application built using the **MERN Stack (MongoDB, Express, React, Node.js)** to organize and manage university hackathons.  
This platform allows teams and participants to register, manage profiles, and view event details seamlessly.

---

## 🚀 Project Overview

The Hackathon Website helps **organizers** manage events and **participants** register as teams or individuals.

### 🎯 Features
- 🔐 **User Authentication (Signup/Login)**  
  - Signup using Registration Number, Email, and Password  
  - Login using Email and Password  
  - JWT-based authentication for secure sessions  

- 🏠 **Homepage**
  - Displays hackathon overview, schedule, and registration links  
  - Navbar with: Home | Problem Statements | Team Registration | Sponsors | About Us | Profile  

- 👥 **Team Registration**
  - Register as a **Solo**, **Duo**, or **Team (3–5 members)**  
  - Team Leader auto-filled from logged-in user  
  - Add team members using Registration Numbers and Emails  
  - Select Problem Statement from a dropdown  

- 🙍‍♂️ **User Profile**
  - View and edit profile details  
  - Change password  
  - Logout option  

- 🧾 **(Optional) Organizer Dashboard**
  - Manage and view all teams and participants  
  - Approve or reject team registrations  
  - Download participant data (CSV)

---

## 🧩 Tech Stack

| Layer | Technology |
|-------|-------------|
| **Frontend** | React, Tailwind CSS / Material UI |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB (Mongoose) |
| **Authentication** | JWT (JSON Web Token) |
| **Hosting (optional)** | Vercel / Render / Netlify / MongoDB Atlas |

---

## ⚙️ Folder Structure

hackathon-website/
├── backend/
│ ├── server.js
│ ├── config/
│ │ └── db.js
│ ├── models/
│ │ ├── User.js
│ │ └── Team.js
│ ├── routes/
│ │ ├── authRoutes.js
│ │ ├── teamRoutes.js
│ │ └── userRoutes.js
│ └── middleware/
│ └── authMiddleware.js
│
└── frontend/
├── src/
│ ├── components/
│ ├── pages/
│ │ ├── Home.jsx
│ │ ├── Login.jsx
│ │ ├── Signup.jsx
│ │ ├── TeamRegister.jsx
│ │ ├── Profile.jsx
│ │ └── About.jsx
│ ├── App.jsx
│ ├── index.jsx
│ └── api/
│ └── axios.js
└── package.json


---

## 🧱 Backend Overview

### 🧍 User Schema
```js
{
  registrationNumber: { type: String, required: true, unique: true },
  email: { type: String, required: true, unique: true },
  password: { type: String, required: true },
}

👥 Team Schema
{
  teamName: { type: String, required: true },
  leader: { type: mongoose.Schema.Types.ObjectId, ref: 'User' },
  members: [{ type: mongoose.Schema.Types.ObjectId, ref: 'User' }],
  problemStatement: { type: String },
  createdAt: { type: Date, default: Date.now }
}

🔗 API Routes
Method	Endpoint	Description
POST	/api/auth/signup	Register a new user
POST	/api/auth/login	Login existing user
GET	/api/users/profile	Get user profile (JWT required)
PUT	/api/users/profile	Update user profile
POST	/api/teams/register	Register a team
GET	/api/teams	Fetch all registered teams
🔒 Authentication Flow

On login/signup, backend returns a JWT token.

Token is stored in localStorage.

Axios interceptors attach the token to every request header.

Backend middleware verifies the token for protected routes.

🎨 Frontend Overview
📄 Pages
Page	Description
Login	Authenticate user with email/password
Signup	Create new account with registration number, email, and password
Home	Overview of hackathon, problem statements, and sponsors
Team Registration	Register solo or as a team
Profile	Edit personal details and logout
About Us	Information about organizers and event goals
🧰 Components

Navbar

Protected Route Wrapper

Registration Form

Profile Form

💡 Future Enhancements

🏆 Leaderboard / Live Updates Section

⏱ Countdown Timer to Hackathon Start

📧 Email Confirmation for Registration

🧑‍💼 Admin Panel for Problem Statements, Sponsors & Teams

🖼 Sponsor Section with dynamic logos

⚡ Getting Started
1️⃣ Clone Repository
git clone https://github.com/yourusername/hackathon-website.git
cd hackathon-website

2️⃣ Install Dependencies
# Backend
cd backend
npm install

# Frontend
cd ../frontend
npm install

3️⃣ Environment Variables

Create .env file inside backend/ with:

PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key

4️⃣ Run the Project
# Run backend
cd backend
npm run dev

# Run frontend
cd ../frontend
npm start


The app will run on:

Frontend → http://localhost:3000

Backend → http://localhost:5000

👨‍💻 Contributors

Your Name – Organizer & Developer

University Hackathon Committee

📜 License

This project is open-source under the MIT License.

“Code. Create. Compete. — Empowering innovation through hackathons!”


---