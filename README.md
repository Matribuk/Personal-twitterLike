# Twitter-Like Social App

A full-stack social media application inspired by Twitter, featuring a Flutter mobile client, Go backend API, and PostgreSQL database.

## 📋 Overview

This project is a social media platform that allows users to create accounts, post messages (chats), and interact with other users.  The application is built with a modern tech stack focusing on scalability and cross-platform compatibility.

## 🏗️ Architecture

The project consists of three main components:

- **Mobile App**: Flutter-based mobile application for iOS and Android
- **Backend API**: RESTful API built with Go and Gin framework
- **Database**: PostgreSQL database with Docker support

## 🚀 Features

- User authentication with JWT tokens
- User profiles with customizable avatars
- Post messages (chats)
- Secure password storage
- RESTful API endpoints
- Cross-origin resource sharing (CORS) support
- Secure storage for sensitive data

## 📁 Project Structure

```
twitter-like/
├── mobile/          # Flutter mobile application
├── api/             # Go backend API
│   ├── cmd/         # Application entry point
│   ├── config/      # Configuration management
│   ├── controllers/ # Request handlers
│   ├── middlewares/ # Authentication and other middlewares
│   ├── models/      # Data models
│   ├── routes/      # API route definitions
│   ├── storage/     # Database connection and queries
│   └── utils/       # Helper functions
└── database/        # PostgreSQL setup and initialization
```

## 🛠️ Tech Stack

### Mobile App
- **Framework**: Flutter 3.5.4+
- **Language**: Dart
- **Key Dependencies**:
  - `http`: HTTP client for API requests
  - `flutter_secure_storage`: Secure local storage
  - `flutter_dotenv`: Environment configuration

### Backend API
- **Language**: Go 1.23.2
- **Framework**: Gin
- **Key Dependencies**:
  - `gin-gonic/gin`: Web framework
  - `dgrijalva/jwt-go`: JWT authentication
  - `lib/pq`: PostgreSQL driver
  - `godotenv`: Environment configuration
  - `gin-contrib/cors`: CORS middleware

### Database
- **Database**: PostgreSQL (latest)
- **Deployment**: Docker & Docker Compose

## 🚦 Getting Started

### Prerequisites

- Go 1.23.2 or higher
- Flutter SDK 3.5.4 or higher
- Docker and Docker Compose
- PostgreSQL (if not using Docker)

### 1. Database Setup

```bash
cd database

# Create environment file
cp .env.exemple .env
# Edit . env with your database credentials

# Start PostgreSQL with Docker
docker-compose up -d
```

The database will be initialized with: 
- Users table
- Chats table
- Default admin user (email: admin@example.com)

### 2. Backend API Setup

```bash
cd api

# Create environment file
cp .env.exemple .env
# Configure your environment variables

# Install dependencies
go mod download

# Run the API server
go run cmd/main. go
```

The API will start on the configured port (check your .env file).

### 3. Mobile App Setup

```bash
cd mobile

# Create environment file
cp .env . env
# Add your API endpoint configuration

# Install dependencies
flutter pub get

# Run the app
flutter run
```

## 🗄️ Database Schema

### Users Table
- `id`: Serial primary key
- `email`: Unique email address
- `nickname`: Unique username
- `url_image`: Profile picture URL (default provided)
- `password`: Hashed password

### Chats Table
- `id`: Serial primary key
- `user_id`: Foreign key to users table
- `message`: Text message content
- `created_at`: Timestamp

## 🔐 Authentication

The application uses JWT (JSON Web Tokens) for authentication.  Authentication tokens are securely stored on the mobile device using Flutter Secure Storage.

## 🌐 API Endpoints

The API supports the following HTTP methods: 
- GET
- POST
- PUT
- DELETE

CORS is enabled for all origins with credentials support.

## 📝 Environment Variables

### Backend API (`api/. env`)
```
# Add your API configuration
# Database connection details
# JWT secret key
# Server port
```

### Database (`database/.env`)
```
POSTGRES_USER=your_username
POSTGRES_PASSWORD=your_password
POSTGRES_DB=your_database_name
```

### Mobile App (`mobile/.env`)
```
# API base URL
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Matribuk**
- GitHub: [@Matribuk](https://github.com/Matribuk)

## 🔮 Future Enhancements

- [ ] Like and retweet functionality
- [ ] User following system
- [ ] Real-time notifications
- [ ] Media upload (images/videos)
- [ ] Direct messaging
- [ ] Search functionality
- [ ] User feed with pagination
- [ ] Comment threads

## 📞 Support

If you have any questions or need help, please open an issue in the GitHub repository. 
```
