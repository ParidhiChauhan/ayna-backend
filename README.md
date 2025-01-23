
# Real-Time Chat Application (Backend)

This is the **Backend** for the **Real-Time Chat Application** built using **Strapi**. It handles user authentication and stores chat messages in a local database. The backend also runs a WebSocket server for real-time messaging.

## Features
- User authentication (register and login)
- Chat session management (create and fetch messages)
- WebSocket server for real-time message communication
- Local database storage for chat history

---

## Requirements
- Node.js (v14 or above)
- npm or yarn
- Strapi (v4.x)

---

## Getting Started


1. Install dependencies: npm install
2. Run the Strapi application: npm run develop
The Strapi admin panel will be available at: http://localhost:1337/admin

3. Configure the Strapi Admin Panel
Log in to the Strapi admin panel using the default admin credentials.
Create the User and ChatSession collections in the Strapi Admin interface using the Content-Type Builder:
User collection: Fields for username, password, and email.
ChatSession collection: Fields for message (string) and a relation to the User model.
4. Set Permissions
Go to Settings → Users & Permissions → Roles.
Under Roles, click on the Public role and ensure the following permissions:
Auth: Allow Register and Login actions.
ChatSession: Allow Find and Create actions.
5. WebSocket Server
The WebSocket server is configured to listen on port 8080. It will echo any message sent from the client and save the message to the Strapi database under the ChatSession model.

API Endpoints
Authentication
POST /api/auth/local/register: Register a new user.
POST /api/auth/local/login: Log in a user.
Chat Sessions
GET /api/chat-sessions: Fetch all chat messages.
POST /api/chat-sessions: Create a new chat message.
