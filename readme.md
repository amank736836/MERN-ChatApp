
# 💬 ChatChamp - MERN Chat Application

Welcome to **ChatChamp**, a real-time chat application built with the MERN stack (MongoDB, Express.js, React.js, Node.js) and Socket.IO for instant communication. It offers features like user authentication, one-to-one and group chats, real-time messaging, and more.

---

## 🌐 Live Demo

👉 [chatchamp.vercel.app](https://chatchamp.vercel.app)

---

## 👨‍💻 Developer

* **Name:** Aman Kumar
* **LinkedIn:** [linkedin.com/in/amank736836](https://www.linkedin.com/in/amank736836)
* **Portfolio:** [amank736836.vercel.app](https://amank736836.vercel.app)
* **Feedback:** [chatchamp.vercel.app/u/amank736836](https://chatchamp.vercel.app/u/amank736836)

---

## 📂 Repositories

* **Main Repository:** [github.com/amank736836/MERN-ChatApp](https://github.com/amank736836/MERN-ChatApp)
* **Frontend:** [github.com/amank736836/MERN-ChatApp-Frontend](https://github.com/amank736836/MERN-ChatApp-Frontend)
* **Backend:** [github.com/amank736836/MERN-ChatApp-Backend](https://github.com/amank736836/MERN-ChatApp-Backend)

---

## 🚀 Features

* **User Authentication:** Secure login and registration with JWT.
* **Real-Time Messaging:** Instant communication using Socket.IO.
* **One-to-One and Group Chats:** Create personal or group conversations.
* **Typing Indicators:** See when others are typing.
* **Online Status:** Real-time user presence.
* **Media Sharing:** Send images and files.
* **Notifications:** Receive alerts for new messages and friend requests.
* **AI Integration:** Smart replies using Google Generative AI SDK.
* **Email Notifications:** Account actions and alerts via Nodemailer.
* **Responsive Design:** Optimized for both desktop and mobile devices.

---

## 🛠️ Tech Stack

* **Frontend:** React.js, Tailwind CSS, Daisy UI
* **Backend:** Node.js, Express.js
* **Database:** MongoDB (Mongoose ODM)
* **Real-Time Communication:** Socket.IO
* **Authentication & Security:** JWT, bcrypt, express-validator, cookie-parser, CORS
* **File Storage:** Multer, Cloudinary SDK
* **Email:** Nodemailer
* **AI SDK:** `@ai-sdk/google`, `ai`
* **Dev Tools:** nodemon, morgan, dotenv, uuid, `@faker-js/faker`

---

## 📦 Installation

### 1. Clone the Repositories

```bash
git clone https://github.com/amank736836/MERN-ChatApp-Backend.git
git clone https://github.com/amank736836/MERN-ChatApp-Frontend.git
```

### 2. Install Dependencies

#### Backend

```bash
cd MERN-ChatApp-Backend
npm install
```

#### Frontend

```bash
cd ../MERN-ChatApp-Frontend
npm install
```

### 3. Configure Environment Variables

Create a `.env` file in both the backend and frontend root directories with the necessary environment variables as listed below.

### 4. Start the Applications

#### Backend

```bash
npm run dev
```

#### Frontend

```bash
npm start
```

---

## 🔧 Environment Variables

### Backend `.env`

```dotenv
# Server & Database
MONGODB_URI=your_mongo_connection_string
PORT=5000
NODE_ENV=development

# JWT & Cookies
JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=7d
JWT_COOKIE_EXPIRES_IN=7
STEALTHY_NOTE_TOKEN_NAME=token_name
STEALTHY_NOTE_ADMIN_TOKEN_NAME=admin_token_name
ADMIN_SECRET_KEY=admin_only_secret

# Client URLs
CLIENT_URL=http://localhost:3000
CLIENT_PRODUCTION_URL=https://chatchamp.vercel.app

# Email (Nodemailer)
NODE_MAILER_EMAIL=your_email@example.com
NODE_MAILER_PASSWORD=your_email_password

# Cloudinary (Media Uploads)
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
CLOUDINARY_URL=your_cloudinary_url

# AI Integration
GOOGLE_GENERATIVE_AI_API_KEY=your_google_ai_key
```

---

### Frontend `.env`

```dotenv
REACT_APP_API_URL=http://localhost:5000/api/v1
```

---

## 📖 API Structure

All API endpoints are prefixed with `/api/v1` to support versioning and maintain backward compatibility.

### 🔐 Authentication Routes

| Method | Endpoint                      | Description                |
| ------ | ----------------------------- | -------------------------- |
| POST   | `/api/v1/user/register`       | Register new user          |
| POST   | `/api/v1/user/login`          | Authenticate & receive JWT |
| POST   | `/api/v1/user/verify`         | Verify user (email/code)   |
| POST   | `/api/v1/user/forgotPassword` | Request password reset     |
| POST   | `/api/v1/user/updatePassword` | Update with new password   |
| GET    | `/api/v1/user/logout`         | Clear auth cookie          |

### 👤 User Routes

> All these routes require a valid session (`isAuthenticated` middleware).

| Method | Endpoint                       | Description                             |
| ------ | ------------------------------ | --------------------------------------- |
| GET    | `/api/v1/user/me`             | Get current user’s profile              |
| GET    | `/api/v1/user/notifications`  | Fetch current user’s notifications      |
| GET    | `/api/v1/user/search`         | Search for other users by name or email |
| GET    | `/api/v1/user/friends`        | List current user’s friends             |
| POST   | `/api/v1/user/sendRequest`    | Send a friend request                   |
| PUT    | `/api/v1/user/acceptRequest`  | Accept a friend request                 |
| POST   | `/api/v1/user/acceptMessages` | Enable/disable accepting messages       |

### 💬 Chat Routes

> All chat routes require user authentication (`isAuthenticated` middleware).

| Method | Endpoint                       | Description                                            |
| ------ | ------------------------------ | ------------------------------------------------------ |
| POST   | `/api/v1/chat/suggestMessages` | Get AI-driven suggestions for the current conversation |
| POST   | `/api/v1/chat/sendMessage`     | Send a new text message                                |
| GET    | `/api/v1/chat`                 | Retrieve list of chats the user is a part of           |
| GET    | `/api/v1/chat/group`           | Retrieve all group chats                               |
| POST   | `/api/v1/chat/group`           | Create a new group chat                                |
| PUT    | `/api/v1/chat/group`           | Add members to an existing group chat                  |
| DELETE | `/api/v1/chat/group`           | Leave a group chat                                     |
| PUT    | `/api/v1/chat/removeMember`    | Remove a member from a group chat                      |
| POST   | `/api/v1/chat/message`         | Send attachments (images/files) to a chat              |
| GET    | `/api/v1/chat/message/:chatId` | Get all messages for a specific chat                   |
| GET    | `/api/v1/chat/:chatId`         | Get chat details (one-to-one or group)                 |
| PUT    | `/api/v1/chat/:chatId`         | Rename a group chat                                    |
| DELETE | `/api/v1/chat/:chatId`         | Delete a chat (one-to-one or group)                    |

---

## 🔌 WebSocket Events

| Event               | Direction         | Description                                                                |
| ------------------- | ----------------- | -------------------------------------------------------------------------- |
| `NEW_MESSAGE`       | ↔ client ↔ server | Send or receive a new chat message.                                        |
| `NEW_MESSAGE_ALERT` | server → client   | Notify client of a message when not in the active chat.                    |
| `REFETCH_CHATS`     | server → client   | Instruct client to reload the chat list (e.g., after creating a new room). |
| `NEW_REQUEST`       | server → client   | Alert client of a new chat invitation or system notification.              |
| `ALERT`             | server → client   | Generic alert channel for system/error notifications.                      |
| `START_TYPING`      | ↔ client ↔ server | Notify when a user begins typing in a chat room.                           |
| `STOP_TYPING`       | ↔ client ↔ server | Notify when a user stops typing.                                           |
| `CHAT_JOINED`       | ↔ client ↔ server | Emitted when a user joins a room; server broadcasts to room members.       |
| `CHAT_LEAVED`       | ↔ client ↔ server | Emitted when a user leaves a room; server broadcasts to room members.      |
| `ONLINE_USERS`      | server → client   | Provides the current list of online users in a room or globally.           |

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/xyz`)
3. Commit your changes (`git commit -m "Add xyz"`)
4. Push to your branch (`git push origin feature/xyz`)
5. Open a Pull Request

Please follow existing code style and include tests where applicable.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---
