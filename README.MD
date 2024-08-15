# Face Recognition App

Welcome to the Face Recognition App, a full-stack web application that allows users to detect faces in images using Clarifai's Face Detection Model. The backend is built with Node.js and Express, and the database management is handled using Knex with PostgreSQL.

## ⭐ Key Features

- **Face Detection**: Integrates with Clarifai's API to detect faces in user-uploaded images.
- **User Authentication**: Secure user registration and sign-in using bcrypt for password hashing.
- **User Profiles**: Tracks the number of images a user has submitted for face detection.
- **PostgreSQL Integration**: Stores user data and image submission entries.

## ⚡ Endpoints

### `/signin`
- **Method**: POST
- **Description**: Handles user sign-in by validating credentials.
- **Payload**:
  ```json
  {
    "email": "user@example.com",
    "password": "password123"
  }
  ```
- **Response**: User data if successful, otherwise an error message.

### `/register`
- **Method**: POST
- **Description**: Handles user registration by creating a new user profile and login credentials.
- **Payload**:
  ```json
  {
    "email": "user@example.com",
    "name": "John Doe",
    "password": "password123"
  }
  ```
- **Response**: Registered user data if successful, otherwise an error message.

### `/image`
- **Method**: PUT
- **Description**: Updates the user's image entry count when a new image is submitted for face detection.
- **Payload**:
  ```json
  {
    "id": "123"
  }
  ```
- **Response**: Updated entry count for the user.

### `/imageurl`
- **Method**: POST
- **Description**: Calls Clarifai's API to detect faces in the provided image URL.
- **Payload**:
  ```json
  {
    "input": "https://example.com/image.jpg"
  }
  ```
- **Response**: Clarifai API response containing face detection data.

## 🚀 Getting Started

### Prerequisites

- Node.js
- PostgreSQL

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/facerecognition.git
   cd facerecognition
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up the database:
   ```sql
   CREATE DATABASE facerecognition;
   ```

4. Create a `.env` file with the following environment variables:
   ```
   CLARIFAI_API_KEY=your_clarifai_api_key
   DATABASE_URL=postgres://user:password@localhost:5432/facerecognition
   ```

5. Start the application:
   ```bash
   npm start
   ```

## ⚙️ Configuration

The application can be configured using environment variables in the `.env` file:

- `CLARIFAI_API_KEY`: Your Clarifai API key.
- `DATABASE_URL`: Connection string for your PostgreSQL database.

## ✨ Tech Stack

- **Frontend**: React.js, Clarifai API
- **Backend**: Node.js, Express.js
- **Database**: PostgreSQL
- **ORM**: Knex.js
- **Authentication**: bcrypt

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 👏 Acknowledgements

- [Clarifai](https://www.clarifai.com/) for the powerful image recognition API.
- [Knex.js](http://knexjs.org/) for SQL query building.

