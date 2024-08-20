
<div align="center">
  <br />
  <a href="https://drive.google.com/file/d/1ZKCV4HLKSkajlb-8CVMIRV3q2_qqW2Gs/view?usp=sharing" target="_blank">
    <img src="https://github.com/adrianhajdin/zoom-clone/assets/67959015/f09a8421-67d3-45ce-b9bc-a791cdc2774b" alt="Project Banner">
  </a>
  
  <br />

  <div>
    <img src="https://img.shields.io/badge/-React_Native-black?style=for-the-badge&logoColor=white&logo=react&color=61DAFB" alt="react-native" />
    <img src="https://img.shields.io/badge/-Node_JS-black?style=for-the-badge&logoColor=white&logo=node.js&color=339933" alt="nodejs" />
    <img src="https://img.shields.io/badge/-MongoDB-black?style=for-the-badge&logoColor=white&logo=mongodb&color=47A248" alt="mongodb" />
    <img src="https://img.shields.io/badge/-Socket.io-black?style=for-the-badge&logoColor=white&logo=socket.io&color=010101" alt="socket.io" />
    <img src="https://img.shields.io/badge/-Tailwind_CSS-black?style=for-the-badge&logoColor=white&logo=tailwindcss&color=06B6D4" alt="tailwindcss" />
  </div>

  <h3 align="center">Chatdong - Full Stack Chat App</h3>

   <div align="center">
     Build your own full-stack chat application using React Native, Node.js, MongoDB, and Socket.io. Check out the design and assets on the link below!
    </div>
</div>

## 📋 <a name="table">Table of Contents</a>

1. 🤖 [Introduction](#introduction)
2. ⚙️ [Tech Stack](#tech-stack)
3. 🔋 [Features](#features)
4. 🤸 [Quick Start](#quick-start)
5. 🕸️ [Assets & Code](#snippets)
6. 🚀 [More](#more)

## <a name="introduction">🤖 Introduction</a>

**Chatdong** is a full-stack chat application built using React Native for the frontend, Node.js for the backend, MongoDB for database management, and Socket.io for real-time communication. This app provides a responsive, real-time chat experience with a modern UI designed with Tailwind CSS.

The project structure consists of two main folders:

- `frontend`: React Native app.
- `backend`: Node.js server with Express and Socket.io.

You can view the design assets and other resources [here](https://drive.google.com/file/d/1ZKCV4HLKSkajlb-8CVMIRV3q2_qqW2Gs/view?usp=sharing).

## <a name="tech-stack">⚙️ Tech Stack</a>

- **React Native**
- **Node.js**
- **MongoDB**
- **Socket.io**
- **Tailwind CSS**

## <a name="features">🔋 Features</a>

👉 **Real-time Chat**: Leveraging Socket.io, the app offers real-time communication between users.

👉 **User Authentication**: Secure user authentication with JWT tokens.

👉 **Responsive Design**: Optimized for both mobile (React Native) and web interfaces.

👉 **Message Storage**: Stores chat history in MongoDB, ensuring messages persist across sessions.

👉 **Group Chats**: Users can create group chats with multiple participants.

👉 **Notification System**: Real-time notifications for new messages and activities.

## <a name="quick-start">🤸 Quick Start</a>

Follow these steps to set up the project locally.

**Prerequisites**

Ensure you have the following installed:

- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/)
- [npm](https://www.npmjs.com/)
- [MongoDB](https://www.mongodb.com/)

**Cloning the Repository**

```bash
git clone https://github.com/Abdullah0Dev/Chatdong.git
cd Chatdong
```

**Setting Up Backend**

```bash
cd backend
npm install
```

Create a `.env` file in the `backend` directory and add the following environment variables:

```env
MONGO_URI=<your_mongodb_uri>
JWT_SECRET=<your_jwt_secret>
```

Start the server:

```bash
npm start
```

**Setting Up Frontend**

```bash
cd ../frontend
npm install
```

Run the app:

```bash
npm start
```

**Tailwind CSS Configuration**

Here’s a snippet from the Tailwind CSS configuration:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        accent: '#fef3ce',
        white: '#ffffff',
        primary: '#110905',
        secondary: '#f7f7f7',
        black: {
          100: '#010411',
          200: '#8d8d8f',
        },
        blue: '#E4F2FD',
        purple: '#eecbd1',
      },
    },
  },
  plugins: [],
};
```

## <a name="snippets">🕸️ Assets & Code</a>

<details>
<summary><code>components/ChatCard.tsx</code></summary>

```typescript
import React from 'react';
import { View, Text } from 'react-native';

const ChatCard = ({ user, message }) => (
  <View className="bg-secondary p-4 mb-2 rounded-lg">
    <Text className="text-primary font-bold">{user}</Text>
    <Text className="text-black-200">{message}</Text>
  </View>
);

export default ChatCard;
```

</details>

<details>
<summary><code>server.js</code></summary>

```javascript
const express = require('express');
const http = require('http');
const socketIo = require('socket.io');
const mongoose = require('mongoose');

require('dotenv').config();

const app = express();
const server = http.createServer(app);
const io = socketIo(server);

mongoose.connect(process.env.MONGO_URI, { useNewUrlParser: true, useUnifiedTopology: true });

io.on('connection', (socket) => {
  console.log('a user connected');
  socket.on('chat message', (msg) => {
    io.emit('chat message', msg);
  });
});

server.listen(3000, () => {
  console.log('listening on *:3000');
});
```

</details>

## <a name="more">🚀 More</a>

Feel free to contribute to the project or suggest new features by opening an issue or a pull request. If you have any questions, reach out to me on [GitHub](https://github.com/Abdullah0Dev). Happy coding!
 
