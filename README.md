# SecureVault 🛡️

> **Academic Project** | Cyber Security Lab Demo

SecureVault is a secure document storage web application designed to demonstrate "military-grade" security principles and aesthetics. It features end-to-end encryption concepts, role-based access control, and multi-factor authentication (MFA) using Email OTPs.

## 🚀 Features

- **Military-Grade Aesthetic**: A visually striking UI with glassmorphism, glowing effects, and smooth animations.
- **Secure Authentication**:
  - User Registration & Login with `bcrypt` password hashing.
  - **2FA / MFA**: Email-based Time-sensitive One-Time Passwords (OTP) via EmailJS.
- **Role-Based Access Control (RBAC)**: Granular permission simulations.
- **Responsive Design**: Fully responsive interface for mobile and desktop using CSS Grid/Flexbox.
- **SQL Database Integration**: Persistent user storage using MySQL.

## 🛠️ Tech Stack

**Frontend:**
- HTML5 & CSS3 (Custom Design System, no external CSS frameworks)
- Vanilla JavaScript (ES6+)
- EmailJS SDK (for client-side OTP emails)
- FontAwesome (Icons) & Google Fonts

**Backend:**
- Node.js
- Express.js
- MySQL2 (Database Driver)
- Bcrypt.js (Password Security)
- Cors (Cross-Origin Resource Sharing)

## ⚙️ Installation & Setup

### Prerequisites
- [Node.js](https://nodejs.org/) (v14 or higher)
- [MySQL Server](https://dev.mysql.com/downloads/installer/)

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/SecureVault.git
cd SecureVault
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Database Setup
1. Open your MySQL interface (Workbench or Command Line).
2. Create the database and table:

```sql
CREATE DATABASE cyber_project;

USE cyber_project;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    password_hash VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```
3. **Configuration**: 
   - Open `db.js`.
   - Update the `createConnection` user and password to match your local MySQL credentials.

### 4. Run the Application
Start the backend server:
```bash
node server.js
```
The server will start on `http://localhost:5000`.
Open your browser and navigate to `http://localhost:5000` to view the application.

## 📂 Project Structure
```
SecureVault/
├── node_modules/       # Dependencies
├── db.js               # Database connection configuration
├── index.html          # Main application interface
├── package.json        # Project metadata and dependencies
├── script.js           # Frontend logic (Auth, UI interactions, API calls)
├── server.js           # Express backend server & API endpoints
└── styles.css          # Custom styling and animations
```

## 🔒 Security Notes
*This is an academic demonstration project.*
- **OTP**: Uses client-side email dispatch for demonstration purposes. In a production environment, OTPs should be generated and sent from the backend to prevent manipulation.
- **Credentials**: Database credentials in `db.js` should be moved to environment variables (`.env`) for production.

