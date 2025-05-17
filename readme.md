
# 💬 MERN ChatApp

A full-stack, real-time chat application built using the MERN stack (MongoDB, Express.js, React.js, Node.js), integrating Socket.IO for live messaging, secure authentication, file sharing, and AI-powered features for an enhanced messaging experience.

**🔗 Live Demo:** [chatchamp.vercel.app](https://chatchamp.vercel.app)
**🧑‍💻 Developer:** [Aman Kumar](https://www.linkedin.com/in/amank736836)
**📬 Feedback:** [Leave anonymous feedback](https://chatchamp.vercel.app/u/amank736836)
**📂 GitHub:** [@amank736836](https://github.com/amank736836)

---

## 🚀 Features

* ⚡ **Real-time Messaging** — Instant chat updates using Socket.IO
* 🔐 **JWT Authentication** — Secure login/signup with password hashing
* 📁 **File Sharing** — Upload and share media files via Cloudinary
* 📩 **Email Notifications** — Account activity alerts via Nodemailer
* 🤖 **AI Integration** — Smart suggestions using Google’s Generative AI
* 📊 **Dashboard Charts** — Insightful data visualizations with Chart.js
* ✨ **Anonymous Messages** — Send anonymous messages to users
* 🧑‍🎨 **Modern UI** — Responsive Material-UI interface with Framer Motion animations

---

## 🛠️ Tech Stack

| Category      | Technologies                                                                                              |
| ------------- | --------------------------------------------------------------------------------------------------------- |
| **Frontend**  | React.js, Redux, Material-UI, Axios, Socket.io-client, Framer Motion, Chart.js                            |
| **Backend**   | Node.js, Express.js, MongoDB, Mongoose, Socket.IO, JWT, Bcrypt, Cloudinary, Nodemailer, Google Gen AI SDK |
| **Dev Tools** | GitHub Actions, Vercel, Postman, dotenv, CORS, cookie-parser                                              |

---

## 📦 Installation

1. **Clone the Repo:**

   ```bash
   git clone https://github.com/amank736836/MERN-ChatApp.git
   cd MERN-ChatApp
   ```

2. **Backend Setup:**

   ```bash
   cd backend
   npm install
   ```

3. **Frontend Setup:**

   ```bash
   cd ../frontend
   npm install
   ```

4. **Environment Variables:**
   Add `.env` files for backend with:

   ```
   MONGO_URI=<Your MongoDB URI>
   JWT_SECRET=<Your JWT Secret>
   CLOUDINARY_API_KEY=<Your Cloudinary Key>
   NODEMAILER_PASS=<Your Email App Password>
   ```

5. **Run App Locally:**

   * Backend: `npm run dev` (from `/backend`)
   * Frontend: `npm start` (from `/frontend`)

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the project
2. Create a new branch (`git checkout -b feature-x`)
3. Commit your changes (`git commit -m 'Add feature x'`)
4. Push to the branch (`git push origin feature-x`)
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## ⭐️ Support

If you found this project helpful, give it a ⭐️ on GitHub and consider connecting with me on [LinkedIn](https://www.linkedin.com/in/amank736836).
Feel free to reach out for any queries or collaborations!

---

## 🔧 Environment Variables

Create a `.env` file in the **backend** directory with the following variables:

```bash
# Server & Database
MONGODB_URI=<Your MongoDB connection string>
PORT=<Server port, e.g. 5000>
NODE_ENV=<development|production>

# Authentication & Cookies
JWT_SECRET=<Your JWT signing secret>
JWT_EXPIRES_IN=<e.g. 7d>
JWT_COOKIE_EXPIRES_IN=<e.g. 7>
STEALTHY_NOTE_TOKEN_NAME=<Your token cookie name>
STEALTHY_NOTE_ADMIN_TOKEN_NAME=<Your admin token cookie name>
ADMIN_SECRET_KEY=<Your admin-only secret key>

# CORS & Client URLs
CLIENT_URL=<Local client URL, e.g. http://localhost:3000>
CLIENT_PRODUCTION_URL=<Production client URL, e.g. https://chatchamp.vercel.app>

# Email (Nodemailer)
NODE_MAILER_EMAIL=<Your email address>
NODE_MAILER_PASSWORD=<Your email password or app-specific password>

# Cloudinary (Media Uploads)
CLOUDINARY_CLOUD_NAME=<Your Cloudinary cloud name>
CLOUDINARY_API_KEY=<Your Cloudinary API key>
CLOUDINARY_API_SECRET=<Your Cloudinary API secret>
CLOUDINARY_URL=<Your full Cloudinary URL if using>

# AI Integration
GOOGLE_GENERATIVE_AI_API_KEY=<Your Google Generative AI SDK key>
````

And in your **frontend** root (where Vite is), create a `.env` (or `.env.local`) with:

```bash
# Vite (frontend) Environment
VITE_SERVER_URL=<Your backend URL, e.g. http://localhost:5000>
VITE_SOCKET_SERVER_URL=<Your Socket.IO server URL, e.g. http://localhost:5000>
