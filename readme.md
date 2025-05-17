# 💬 MERN ChatApp (ChatChamp)

A full‑stack, real‑time anonymous chat application built with the MERN stack (MongoDB, Express.js, React.js, Node.js). It integrates Socket.IO for live messaging, JWT for secure authentication, Cloudinary for media uploads, Nodemailer for email notifications, and Google’s Generative AI SDK for AI‑driven features. Enjoy a responsive Material‑UI frontend with Redux state management and a powerful Express‑based backend with admin and social APIs. 💬🔒🤖

**👨‍💻 Developer:** [Aman Kumar](https://www.linkedin.com/in/amank736836)  
**📝 Feedback:** [chatchamp.vercel.app/u/amank736836](https://chatchamp.vercel.app/u/amank736836)  
**🔗 Live Demo:** [chatchamp.vercel.app](https://chatchamp.vercel.app)  
**🧑‍💻 Frontend Repo:** [github.com/amank736836/MERN-ChatApp-Frontend](https://github.com/amank736836/MERN-ChatApp-Frontend)  
**🧑‍💻 Backend Repo:** [github.com/amank736836/MERN-ChatApp-Backend](https://github.com/amank736836/MERN-ChatApp-Backend)

---

## 🚀 Core Features

- **💬 Anonymous & Authenticated Chat** – Public/private rooms powered by Socket.IO
- **🔒 Secure Auth** – JWT login/signup, bcrypt hashing, HTTP-only cookies
- **🤖 AI Replies** – Smart message suggestions via Google Generative AI SDK
- **📁 Media Sharing** – File/image upload with Multer & Cloudinary
- **📧 Email Alerts** – Notifications and invitations via Nodemailer
- **👥 Social** – Friend requests, notifications, password recovery
- **👑 Admin Panel** – Stats, user/chat/message management
- **📱 Responsive UI** – Material‑UI + Framer Motion animations
- **🛠️ State Management** – Redux Toolkit on the frontend

---

## 🛠️ Tech Stack

| Layer        | Technologies                                                                                                                                         |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Backend**  | Node.js, Express.js, MongoDB (Mongoose), Socket.IO, JWT, bcrypt, Multer, Cloudinary, Nodemailer, Google Gen AI SDK                                   |
| **Frontend** | React.js (Vite), Redux Toolkit, React Router v7, Material‑UI, @emotion, Framer Motion, react-hot-toast, Socket.IO Client, Axios, Chart.js, moment.js |

---

## 📦 Installation & Setup

### 1. Clone Both Repos

```bash
git clone https://github.com/amank736836/MERN-ChatApp-Backend.git
git clone https://github.com/amank736836/MERN-ChatApp-Frontend.git
```

---

### 2. Backend Setup

```bash
cd MERN-ChatApp-Backend
npm install
# Create .env per below
npm run dev    # development (nodemon)
# or
npm start      # production
```

#### Backend Environment Variables (`/backend/.env`)

```env
MONGODB_URI=your_mongo_uri
PORT=5000
NODE_ENV=development

JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=7d
JWT_COOKIE_EXPIRES_IN=7

ADMIN_SECRET_KEY=your_admin_key

CLIENT_URL=http://localhost:3000
CLIENT_PRODUCTION_URL=https://chatchamp.vercel.app

NODE_MAILER_EMAIL=you@example.com
NODE_MAILER_PASSWORD=app_password

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

GOOGLE_GENERATIVE_AI_API_KEY=your_ai_key
```

---

### 3. Frontend Setup

```bash
cd MERN-ChatApp-Frontend
npm install
# Create .env.local per below
npm run dev                  # development
# or
npm run build && npm run preview  # production preview
```

#### Frontend Environment Variables (`/.env.local`)

```env
VITE_SERVER_URL=http://localhost:5000
VITE_SOCKET_SERVER_URL=http://localhost:5000
```

---

## 📖 API & Routes Overview

All HTTP endpoints are prefixed with `/api/v1`.

### Auth 🔑

- `POST   /api/v1/user/new`
- `POST   /api/v1/user/login`
- `POST   /api/v1/user/verify`
- `POST   /api/v1/user/forgotPassword`
- `POST   /api/v1/user/updatePassword`

### User 👥 (auth required)

- `GET    /api/v1/user/me`
- `GET    /api/v1/user/notifications`
- `GET    /api/v1/user/search`
- `GET    /api/v1/user/friends`
- `PUT    /api/v1/user/sendRequest`
- `PUT    /api/v1/user/acceptRequest`
- `POST   /api/v1/user/acceptMessages`
- `GET    /api/v1/user/logout`

### Admin 👑 (auth required)

- `POST   /api/v1/admin/verify`
- `GET    /api/v1/admin/logout`
- `GET    /api/v1/admin/`
- `GET    /api/v1/admin/stats`
- `GET    /api/v1/admin/users`
- `GET    /api/v1/admin/chats`
- `GET    /api/v1/admin/messages`

### Chat 💥 (auth required)

- `POST   /api/v1/chat/suggestMessages`
- `POST   /api/v1/chat/sendMessage`
- `GET    /api/v1/chat`
- `GET    /api/v1/chat/group`
- `POST   /api/v1/chat/group`
- `PUT    /api/v1/chat/group`
- `DELETE /api/v1/chat/group`
- `PUT    /api/v1/chat/removeMember`
- `POST   /api/v1/chat/message`
- `GET    /api/v1/chat/message/:chatId`
- `GET    /api/v1/chat/:chatId`
- `PUT    /api/v1/chat/:chatId`
- `DELETE /api/v1/chat/:chatId`

---

## 🔌 WebSocket Events

| Event               | Description                         |
| ------------------- | ----------------------------------- |
| `NEW_MESSAGE`       | Send/receive chat message           |
| `NEW_MESSAGE_ALERT` | Alert when off‑chat messages arrive |
| `REFETCH_CHATS`     | Reload chat list                    |
| `NEW_REQUEST`       | New chat invitation                 |
| `ALERT`             | System/error alerts                 |
| `START_TYPING`      | User started typing                 |
| `STOP_TYPING`       | User stopped typing                 |
| `CHAT_JOINED`       | User joined a room                  |
| `CHAT_LEAVED`       | User left a room                    |
| `ONLINE_USERS`      | Broadcast list of online users      |

---

## 🤝 Contributing

1. Fork the project
2. Create a feature branch (`git checkout -b feature/xyz`)
3. Commit your changes (`git commit -m "Add xyz"`)
4. Push to your branch (`git push origin feature/xyz`)
5. Open a Pull Request 📬

Please adhere to existing code conventions and add tests where applicable.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE). ❤️

```

```
