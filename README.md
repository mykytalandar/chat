# Chat

A lightweight real-time chat application that allows users to create chat rooms, join existing channels, and communicate with other users instantly.

## Features

- **Username Setup** — users enter a username when accessing the application for the first time.
- **Room Creation** — create new chat rooms with custom names.
- **Room Renaming** — users can change the names of existing chat rooms.
- **System Notifications** — automatically display a system message in the chat when a room name is changed.
- **Join Rooms** — join existing chat rooms and participate in conversations.
- **Real-Time Messaging** — send and receive messages instantly using WebSocket communication.
- **Room Updates** — automatically synchronize room information across connected clients.
- **System Messages** — display notifications when users join a room.
- **In-Memory Data Storage** — chat rooms, messages, and room participants are stored in server memory and reset when the backend server restarts.

## Tech Stack

### Frontend
- React 19
- TypeScript
- Vite
- React Router
- Axios
- Lucide React
- WebSocket API

### Backend
- Node.js
- Express 5
- WebSocket (`ws`)
- EventEmitter
- CORS
- Nodemon

## Architecture

The application consists of two main parts:

- **Frontend** — a React application responsible for the user interface, navigation, and real-time communication with the backend.
- **Backend** — an Express server that handles application requests and manages WebSocket connections.

WebSocket provides bidirectional communication between the frontend and backend, allowing users to receive room updates and messages without repeatedly polling the server.

The backend uses Node.js EventEmitter to handle application events, including username setup, room creation, and joining rooms.

Room data, connected users, and messages are currently stored in server memory.

## Project Structure

```text
Chat/
├── backend/
│   ├── index.js
│   └── package.json
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
│
└── README.md
```

## Getting Started

### Prerequisites

- Node.js
- npm

### Installation

Clone the repository:

```bash
git clone https://github.com/mykytalandar/chat.git
cd Chat
```

Install backend dependencies:

```bash
cd backend
npm install
```

Install frontend dependencies:

```bash
cd ../frontend
npm install
```

### Environment Variables

Create a `.env` file in the backend directory based on the provided .env.example file.

```text
CLIENT_HOST=http://localhost:5173
```

Important: Set CLIENT_HOST to the frontend development URL provided by Vite when running npm run dev.

For example, Vite usually starts the frontend at http://localhost:5173. If Vite uses a different port, update CLIENT_HOST accordingly.

### Running the Application

Start the backend server:

```bash
cd backend
npm start
```

The backend server runs on:

```text
http://localhost:3005
```

Start the frontend development server in a separate terminal:

```bash
cd frontend
npm run dev
```

Vite will provide a local development URL in the terminal.

## Notes

- Usernames are stored locally in the browser using LocalStorage.
- Chat rooms and messages are stored in memory using JavaScript arrays. All data is lost when the backend server restarts.
- The application does not currently use a database or persistent storage for chat data.

## Author

Developed as a learning project to explore full-stack web development and real-time communication using React, TypeScript, Node.js, and WebSockets.

