# Notes API

This is a RESTful API for user authentication and note management. Users can sign up, log in, log out, create, update, delete, and search for notes.

## Hosted API
The API is hosted [here](https://capstonebackend-p96k.onrender.com).

## Table of Contents
- [Features](#features)
- [Technologies](#technologies)
- [Getting Started](#getting-started)
- [Environment Variables](#environment-variables)
- [API Endpoints](#api-endpoints)
- [Error Handling](#error-handling)

## Features
- **User Authentication**: Sign up, sign in, and sign out with JWT-based token authentication.
- **Note Management**: CRUD operations for notes, search, and pin/unpin feature.
- **Error Handling**: Comprehensive error handling across endpoints.

## Technologies
- **Node.js** with **Express.js** for the server and routing.
- **MongoDB** with **Mongoose** for database management.
- **bcryptjs** for password hashing.
- **jsonwebtoken** for token-based authentication.
- **dotenv** for environment variable management.
- **cookie-parser** for handling cookies.
- **CORS** configured for cross-origin requests.

## Getting Started

### Prerequisites
- Node.js
- MongoDB instance
- Environment configuration file

### Installation
1. Clone this repository:
    ```bash
    git clone <repository_url>
    cd <project_directory>
    ```
2. Install dependencies:
    ```bash
    npm install
    ```
3. Start the development server:
    ```bash
    npm start
    ```

## Environment Variables
Create a `.env` file in the project root and add the following variables:
```plaintext
MONGO_URI=<your_mongodb_connection_string>
JWT_SECRET=<your_jwt_secret>



API Endpoints
Auth Routes
POST /api/auth/signup

Registers a new user.
Body: { username, email, password }
POST /api/auth/signin

Authenticates an existing user.
Body: { email, password }
GET /api/auth/signout

Logs out the user.
Note Routes
POST /api/note/add

Adds a new note (requires token).
Body: { title, content, tags }
POST /api/note/edit/:noteId

Edits a note by ID (requires token).
Body: { title, content, tags, isPinned }
GET /api/note/all

Retrieves all notes of the authenticated user, sorted by pinned status (requires token).
DELETE /api/note/delete/:noteId

Deletes a note by ID (requires token).
PUT /api/note/update-note-pinned/:noteId

Updates the pinned status of a note (requires token).
Body: { isPinned }
GET /api/note/search

Searches notes by title or content (requires token).
Query Parameter: query=<search_term>
Error Handling
Custom error handler provides status codes and error messages for invalid requests or missing data.
