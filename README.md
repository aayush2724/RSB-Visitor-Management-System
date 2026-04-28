<div align="center">
  
# 🛡️ SECURE Visitor Management System
**Next-Generation Cyberpunk-Themed Enterprise Visitor & Security Tracking**

[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org)
[![Express](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Twilio](https://img.shields.io/badge/Twilio-F22F46?style=for-the-badge&logo=twilio&logoColor=white)](https://twilio.com/)
[![Cloudinary](https://img.shields.io/badge/Cloudinary-3448C5?style=for-the-badge&logo=cloudinary&logoColor=white)](https://cloudinary.com/)
[![Deployed on Render](https://img.shields.io/badge/Render-46E3B7?style=for-the-badge&logo=render&logoColor=white)](https://secure-visitor-management.onrender.com/)

<br/>

</div>

---

## 🌌 Overview

SECURE is a fully modernized, cyberpunk-styled full-stack application designed to replace legacy paper-based visitor logs in corporate environments. 

It handles end-to-end visitor processing: from initial registration and hardware-locked photo capture, to automated WhatsApp/Email background notifications, secure administrative dashboards, and pre-scheduled visitor entry logic. 

---

## 🏗️ System Architecture (MVC)

The backend has been restructured into a professional **Model-View-Controller (MVC)** architecture for maximum maintainability and scalability.

```text
RSB-Visitor-Management-System/
├── backend/
│   ├── config/              # Database connection logic
│   ├── controllers/         # Business logic & Route handlers
│   ├── middleware/          # Security & Auth filters
│   ├── models/              # Mongoose Data Schemas
│   ├── routes/              # Express Route definitions
│   └── server.js            # Application Entry Point
└── frontend/                # View Layer (Vanilla HTML/CSS/JS)
```

---

## 🛡️ Enhanced Security Suite

- **Authenticated API Access**: All administrative routes are protected by a server-side **Auth Middleware** requiring a secret Bearer Token.
- **Brute-Force Protection**: Implements `express-rate-limit` on the login gateway to prevent automated credential testing.
- **Production-Grade Headers**: Powered by `Helmet.js` to protect against common web vulnerabilities (XSS, Clickjacking, etc.).
- **Encrypted Env Handling**: Sensitive credentials like `ADMIN_SECRET_TOKEN` are managed exclusively through environment variables.

---

## ✨ Core Features

- **Biometric Identity Capture**: Custom JavaScript hooks into the device's webcam to snap live photos, instantly buffering to Cloudinary.
- **Dynamic Check-in Pass & QR Code**: Generates an entry QR Code unique to each visitor, stored in Cloudinary for rapid fetching.
- **Background Async Notifications**: Fires off HTML Emails via `Nodemailer` and direct WhatsApp tickets via `Twilio` the second a visitor checks in.
- **Intelligence Dashboard**: 
  - Live real-time KPI statistics.
  - Search & filtering, immediate entry/exit logging toggles.
  - One-click `.xlsx` exporting.
- **Pre-Clearance Schedule Portal**: Allows hosts to pre-approve future dates for incoming guests.

---

## 🚀 Deployment Instructions (Render + MongoDB Atlas)

### 1. Database Setup
1. Create a free cluster on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Whitelist `0.0.0.0/0` in Network Access.
3. Copy your connection string (`mongodb+srv://...`).

### 2. Render Setup
1. Sign in to [Render](https://render.com) and create a **New Web Service**.
2. Connect this GitHub repository.
3. Use the following build/start commands:
   - **Build Command**: `cd backend && npm install`
   - **Start Command**: `cd backend && node server.js`
4. Add the **Environment Variables** listed below.

### Required Environment Variables
```env
# Core
PORT=3000
MONGODB_URI=your_mongodb_atlas_uri
BASE_URL=https://your-app.onrender.com
ADMIN_PASSWORD=your_secure_pin
ADMIN_SECRET_TOKEN=generate_a_random_long_string

# Cloudinary
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Messaging
TWILIO_ACCOUNT_SID=your_sid
TWILIO_AUTH_TOKEN=your_token
TWILIO_WHATSAPP_NUMBER=your_twilio_number
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password
HR_EMAIL=recipient@gmail.com
```

---

## 🐳 Docker Deployment

1. **Ensure Docker is Installed**
2. **Configure Environment** (.env in root)
3. **Build and Run**
   ```bash
   docker-compose up -d --build
   ```
4. **Access**: `http://localhost:3000`

---

## 💻 Local Development Setup

1. **Clone & Install**
   ```bash
   git clone https://github.com/aayush2724/RSB-Visitor-Management-System.git
   cd RSB-Visitor-Management-System/backend
   npm install
   ```
2. **Configure .env** in the `/backend` folder.
3. **Run**
   ```bash
   npm start
   ```

---

<div align="center">
  <i>Engineered with 💻 and lots of neon glow</i>
</div>
