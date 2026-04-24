# MERN Chat Application

A real-time chat application built with the MERN stack (MongoDB, Express, React, Node.js) featuring authentication, real-time messaging with Socket.io, and a modern UI.

## Features

- **Authentication & Authorization** — JWT-based login and signup
- **Real-time Messaging** — Instant message delivery via Socket.io
- **Online User Status** — See who's currently online
- **Conversation List** — View and select previous conversations
- **Message History** — Persistent chat history stored in MongoDB
- **Modern UI** — TailwindCSS + DaisyUI responsive design

## Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | React, Vite, TailwindCSS, DaisyUI |
| Backend | Node.js, Express |
| Database | MongoDB (Mongoose ODM) |
| Real-time | Socket.io |
| State | Zustand |
| Auth | JWT + Cookies |

## Project Structure

```
mern-chat-app/
├── backend/
│   ├── controllers/      # Route handlers
│   ├── db/               # MongoDB connection
│   ├── middleware/      # Auth middleware
│   ├── models/          # Mongoose models
│   ├── routes/          # API routes
│   ├── socket/          # Socket.io configuration
│   ├── utils/           # Helper functions
│   └── server.js        # Entry point
├── frontend/
│   ├── src/
│   │   ├── components/  # React components
│   │   ├── context/     # React context providers
│   │   ├── hooks/       # Custom hooks
│   │   ├── pages/       # Page components
│   │   ├── utils/       # Utility functions
│   │   └── zustand/     # State management
│   └── vite.config.js   # Vite configuration
└── package.json         # Root scripts
```

## Prerequisites

- Node.js (v18+)
- MongoDB (local or Atlas)
- npm or yarn

## Installation

### 1. Clone the repository

```bash
git clone <repository-url>
cd mern-chat-app
```

### 2. Install dependencies

```bash
# Install root dependencies
npm install

# Install frontend dependencies
cd frontend && npm install
```

### 3. Configure environment variables

Create a `.env` file in the `backend` directory:

```env
PORT=5000
MONGO_DB_URI=mongodb://localhost:27017/chatapp
JWT_SECRET=your-super-secret-key
NODE_ENV=development
```

> **Note:** Replace `MONGO_DB_URI` with your MongoDB Atlas connection string if using cloud.

### 4. Start the application

**Development mode (two terminals):**

```bash
# Terminal 1: Start backend
npm run server

# Terminal 2: Start frontend
cd frontend && npm run dev
```

**Production mode:**

```bash
npm run build
npm start
```

## API Endpoints

### Authentication
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/signup` | Register new user |
| POST | `/api/auth/login` | User login |
| POST | `/api/auth/logout` | User logout |

### Messages
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/messages/:id` | Get conversation messages |
| POST | `/api/messages/send/:id` | Send a message |

### Users
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/users` | Get all users for sidebar |

## Socket Events

| Event | Direction | Description |
|-------|-----------|-------------|
| `newMessage` | Server → Client | Receive new message |
| `getOnlineUsers` | Server → Client | Online user list |
| `connection` | Client → Server | User connects |
| `disconnect` | Client → Server | User disconnects |

## Ports

| Service | Port | URL |
|---------|------|-----|
| Frontend (Vite) | 5173 | http://localhost:5173 |
| Backend (Express) | 5000 | http://localhost:5000 |

## License

MIT License — © 2024 Burak