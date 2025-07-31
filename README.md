<div align="center">

# QUICK-CHAT 💬

Real-Time Messaging, Instant Connections

![Last Commit](https://img.shields.io/github/last-commit/elyse502/quick-chat?style=flat-square) 
![Languages](https://img.shields.io/github/languages/top/elyse502/quick-chat?style=flat-square&color=blue)
![License](https://img.shields.io/github/license/elyse502/quick-chat?style=flat-square)

*Powered by cutting-edge technologies:*

![Socket.io](https://img.shields.io/badge/Socket.io-010101?style=flat-square&logo=socket.io&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)

## LIVE - DEMO 🌐
Visit the 👉 [_LINK 🔗_](https://quick-chat-nine-beta.vercel.app)

</div>

<br /><hr /><br />

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Environment Variables](#environment-variables)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Real-Time Events](#real-time-events)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Quick-Chat is a full-stack real-time chat application that enables instant messaging with features like:

- 🔐 Secure user authentication
- ⚡ Real-time message delivery
- 👥 User profiles and status
- 📱 Responsive design for all devices
- 🔄 Message history persistence
- 🔊 Notification system

Built with modern web technologies to deliver a seamless chatting experience.

---

## Key Features

### Real-Time Communication
- Instant message delivery with Socket.io
- Typing indicators
- Online/offline status
- Read receipts

### User Experience
- Clean, modern interface
- Responsive design
- Dark/light mode
- Emoji support
- Message search

### Security
- JWT authentication
- Password encryption
- Protected routes
- Session management

### Advanced Functionality
- Message history
- User profiles
- Notification system
- Image/file sharing (via Cloudinary)

---

## Tech Stack

### Frontend
- **React** with Vite
- **Socket.io-client** for real-time updates
- **Context API** for state management
- **Axios** for HTTP requests
- **Tailwind CSS** for styling
- **React Icons** for beautiful icons

### Backend
- **Node.js** with **Express**
- **Socket.io** for WebSocket communication
- **MongoDB** with **Mongoose**
- **JWT** for authentication
- **Bcrypt** for password hashing
- **Cloudinary** for media storage

### DevOps
- **Vercel** for frontend hosting
- **Render** for backend hosting
- **GitHub Actions** for CI/CD

---

## Project Structure

```groovy
quick-chat/
├── client/                  # Frontend application
│   ├── public/             # Static assets
│   ├── src/
│   │   ├── assets/         # Images, icons
│   │   ├── components/     # Reusable components
│   │   │   ├── ChatContainer.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   └── RightSidebar.jsx
│   │   ├── context/        # Global state
│   │   │   ├── AuthContext.jsx
│   │   │   └── ChatContext.jsx
│   │   ├── lib/            # Utilities
│   │   │   └── utils.js
│   │   ├── pages/          # Route pages
│   │   │   ├── HomePage.jsx
│   │   │   ├── LoginPage.jsx
│   │   │   └── ProfilePage.jsx
│   │   └── ...             # Other config files
│
├── server/                 # Backend application
│   ├── controllers/        # Business logic
│   │   ├── messageController.js
│   │   └── userController.js
│   ├── lib/                # Utilities
│   │   ├── cloudinary.js
│   │   ├── db.js
│   │   └── utils.js
│   ├── middleware/         # Auth middleware
│   │   └── auth.js
│   ├── models/             # Database models
│   │   ├── Messages.js
│   │   └── User.js
│   ├── routes/             # API routes
│   │   ├── messageRoutes.js
│   │   └── userRoutes.js
│   └── ...                 # Other server files
```

---

## Getting Started

### Prerequisites

- Node.js (v18+)
- npm (v9+)
- MongoDB Atlas account or local MongoDB
- Cloudinary account (for media storage)

### Installation

1. Clone the repository:
```console
git clone https://github.com/elyse502/quick-chat.git
cd quick-chat
```

2. Install dependencies for both client and server:
```console
# Install client dependencies
cd client && npm install

# Install server dependencies
cd ../server && npm install
```

3. Set up environment variables:
Create `.env` files in both `client` and `server` directories with required credentials.

### Environment Variables

**Server (.env)**
```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
PORT=5000
```

**Client (.env)**
```env
VITE_API_BASE_URL=http://localhost:5000
VITE_SOCKET_URL=http://localhost:5000
```

4. Start the development servers:
```console
# In one terminal (server)
cd server && npm run dev

# In another terminal (client)
cd client && npm run dev
```

---

## Usage

1. **Register/Login**: Create an account or log in
2. **Find Contacts**: Search for other users
3. **Start Chatting**: Select a contact and begin messaging
4. **Real-Time Updates**: See messages appear instantly
5. **Profile Management**: Update your profile picture and status

---

## API Endpoints

### Authentication
| Method | Endpoint          | Description          |
|--------|-------------------|----------------------|
| POST   | /api/auth/register| Register new user    |
| POST   | /api/auth/login   | Login user           |

### Users
| Method | Endpoint          | Description          |
|--------|-------------------|----------------------|
| GET    | /api/users        | Get all users        |
| GET    | /api/users/:id    | Get specific user    |
| PUT    | /api/users/:id    | Update user          |

### Messages
| Method | Endpoint           | Description          |
|--------|--------------------|----------------------|
| GET    | /api/messages/:chatId | Get chat messages |
| POST   | /api/messages      | Send new message    |

---

## Real-Time Events

### Emitted Events
- `new-user` - When a user connects
- `send-message` - When sending a message
- `typing` - When user is typing
- `stop-typing` - When user stops typing

### Received Events
- `receive-message` - When receiving a message
- `user-connected` - When another user connects
- `user-typing` - When another user is typing

---

## Deployment

### Frontend
[![Deploy with Vercel](https://vercel.com/button)](https://quick-chat-nine-beta.vercel.app)

### Backend
Deploy to Render, Vercel, or other Node.js hosting services with MongoDB connection.

---

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---


## License

Distributed under the MIT License. See [LICENSE](https://github.com/elyse502/quick-chat/blob/main/LICENSE) for more information.

---

## 📞 Contact
For any questions or support, please contact:
- [**NIYIBIZI Elysée**](https://linktr.ee/niyibizi_elysee)👨🏿‍💻 | [Github](https://github.com/elyse502) | [Linkedin](https://www.linkedin.com/in/niyibizi-elys%C3%A9e/) | [Twitter](https://twitter.com/Niyibizi_Elyse).
- **Email**: <elyseniyibizi502@gmail.com>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/niyibizi-elys%C3%A9e/) [![@phenrysay](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/Niyibizi_Elyse) [![pH-7](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/elyse502)

---

<div align="center">

**Quick-Chat** - Where conversations happen in real-time! 🚀✨

**Made with ❤️ by <i>[Elysée NIYIBIZI](https://elyse502.github.io/Elysee-Portfolio/)</i>**

[⬆ Back to Top](#table-of-contents)

</div>





