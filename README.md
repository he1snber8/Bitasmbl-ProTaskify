# Bitasmbl-ProTaskify

Develop a professional web-based task management application using React for frontend and Node.js/Express.js on backend, with PostgreSQL for persistent storage. Key features include JWT-based user authentication, project-scoped CRUD operations, and priority-driven task views via RESTful APIs.

## Tech Stack

- Express.js
- PostgreSQL
- React
- Node.js

## Requirements

- Implement JWT authentication for secure user login (Hint: Use jsonwebtoken library to sign and verify tokens)
- Design RESTful CRUD APIs for tasks and projects (Hint: Use Express.js routing and controllers)
- Model relational data in PostgreSQL (Hint: Use pg library for queries)
- Implement front-end state management (Hint: Use React hooks and context)

## Installation

1. Clone the repository:
   
   git clone https://github.com/your-username/Bitasmbl-ProTaskify.git
   cd Bitasmbl-ProTaskify
   
2. Setup Backend:
   
   cd server
   npm install
   
3. Setup Frontend:
   
   cd ../client
   npm install
   
4. Create a `.env` file in the `server` directory with the following variables:
   
   PORT=5000
   DATABASE_URL=postgresql://<username>:<password>@<host>:<port>/<database>
   JWT_SECRET=<your_jwt_secret>
   
5. Initialize the database schema (run SQL scripts or migrations).

## Usage

1. Start the backend server:
   
   cd server
   npm run dev
   
2. Start the frontend application:
   
   cd client
   npm start
   
3. Access the app at `http://localhost:3000`.
4. Register a new user, log in, create projects, and manage tasks with priorities.

## Implementation Steps

1. Initialize the Express.js server (`server/index.js`) and configure middleware (CORS, JSON parsing).
2. Configure PostgreSQL connection using the `pg` library.
3. Create database tables for users, projects, and tasks with relational constraints.
4. Implement authentication routes and controllers (`/api/auth/register`, `/api/auth/login`) using `jsonwebtoken`.
5. Develop project routes and controllers for CRUD operations (`/api/projects`).
6. Develop task routes and controllers scoped under projects (`/api/projects/:projectId/tasks`).
7. Protect routes with JWT middleware to verify tokens.
8. Scaffold the React application in the `client` folder.
9. Create React context for auth state and global state management.
10. Build API service modules to interact with backend endpoints.
11. Implement React components for login, project dashboard, and task manager with priority filters.
12. Test end-to-end functionality and handle error states.

## API Endpoints

### Authentication

- POST `/api/auth/register` - Register a new user
- POST `/api/auth/login` - Authenticate user and return JWT

### Projects

- GET `/api/projects` - Get all projects for authenticated user
- POST `/api/projects` - Create a new project
- GET `/api/projects/:projectId` - Get a single project
- PUT `/api/projects/:projectId` - Update a project
- DELETE `/api/projects/:projectId` - Delete a project

### Tasks

- GET `/api/projects/:projectId/tasks` - List tasks in a project
- GET `/api/projects/:projectId/tasks/:taskId` - Get task details
- POST `/api/projects/:projectId/tasks` - Create a new task
- PUT `/api/projects/:projectId/tasks/:taskId` - Update a task
- DELETE `/api/projects/:projectId/tasks/:taskId` - Delete a task