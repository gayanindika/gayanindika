- 👋 Hi, I’m @gayanindika
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
gayanindika/gayanindika is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
touch README.md
# Chat App

A simple real-time chat application using Node.js, Express, Socket.IO, and React.

## Features
- Real-time messaging.
- Easy setup and deployment.

## How to Run
1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd backend
node index.js
cd frontend
npm start
git add README.md  
git commit -m "Add README"  
git push origin main  
mkdir backend frontend
const express = require('express');
const http = require('http');
const { Server } = require('socket.io');
const app = express();
const server = http.createServer(app);
const io = new Server(server);

io.on('connection', (socket) => {
    socket.on('message', (msg) => io.emit('message', msg));
});

server.listen(3001, () => console.log('Server running on port 3001'));
import { useState, useEffect } from 'react';
import { io } from 'socket.io-client';
const socket = io('http://localhost:3001');

function App() {
    const [message, setMessage] = useState('');
    const [messages, setMessages] = useState([]);

    useEffect(() => {
        socket.on('message', (msg) => setMessages((prev) => [...prev, msg]));
    }, []);

    const sendMessage = () => {
        socket.emit('message', message);
        setMessage('');
    };

    return (
        <div>
            {messages.map((msg, i) => <p key={i}>{msg}</p>)}
            <input value={message} onChange={(e) => setMessage(e.target.value)} />
            <button onClick={sendMessage}>Send</button>
        </div>
    );
}

export default App;
git add .  
git commit -m "Add code structure"  
git push origin main  
tree
.
├── backend/
│   ├── index.js
├── frontend/
│   ├── src/
│   │   ├── App.js
├── README.md
