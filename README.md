# My-Journal-
# 📝 Spring Boot Journal App

A secure and user-friendly **journal application** built using **Spring Boot**, **MongoDB**, and **Spring Security**. Users can register, log in securely (with encrypted passwords), write journal entries, and optionally retrieve data from an **external API** (like motivational quotes, weather, or GPT-based tips).

---

## 🚀 Features

- ✅ User Registration & Login
- 🔐 Password Encryption with BCrypt
- 🔒 Authentication & Authorization via Spring Security
- 🧾 MongoDB for storing journal entries and user data
- 🌐 External API Integration (e.g., quotes, weather, GPT tips)
- ✍️ CRUD for Journal Entries (Create, Read, Update, Delete)
- 🗓️ Timestamps for each entry
- 🧰 RESTful API design

---

## 🧰 Tech Stack

- **Java 17+**
- **Spring Boot**
- **Spring Security**
- **Spring Data MongoDB**
- **BCryptPasswordEncoder**
- **MongoDB** (local or cloud e.g., MongoDB Atlas)
- **Maven**
- **Postman** (for testing)

---

## 🔐 Security

- Passwords are encrypted using `BCrypt`.
- JWT or Session-based Authentication (customizable).
- Spring Security guards all endpoints.
- Role-based security (if needed).
- External API keys stored securely in `application.properties`.

---

## 🌐 API Endpoints

### Authentication
```
POST   /api/auth/register
POST   /api/auth/login
```

### Journal
```
GET    /api/journal              - List all journal entries of the logged-in user
POST   /api/journal              - Create new journal entry
PUT    /api/journal/{id}         - Update an entry by ID
DELETE /api/journal/{id}         - Delete an entry by ID
```

### External API (example)
```
GET /api/quote                   - Fetch a motivational quote
```

---

## ⚙️ Getting Started

### 🧾 Prerequisites
- Java 17+
- Maven
- MongoDB (local or Atlas cloud instance)

### 🔧 Setup

1. Clone the repository:
```bash
git clone https://github.com/yourusername/journal-app.git
cd journal-app
```

2. Configure MongoDB in `application.properties`:
```properties
spring.data.mongodb.uri=mongodb://localhost:27017/journaldb

spring.security.jwt.secret=your_jwt_secret_here
external.api.url=https://api.example.com/quote
external.api.key=your_api_key_here
```

> If you're using MongoDB Atlas:
```properties
spring.data.mongodb.uri=mongodb+srv://<username>:<password>@cluster0.mongodb.net/journaldb?retryWrites=true&w=majority
```

3. Run the app:
```bash
mvn spring-boot:run
```

---

## 📦 Sample JSON Requests

### Register
```json
POST /api/auth/register
{
  "username": "john_doe",
  "password": "strongPass123"
}
```

### Login
```json
POST /api/auth/login
{
  "username": "john_doe",
  "password": "strongPass123"
}
```

### Create Journal Entry
```json
POST /api/journal
{
  "title": "My First Entry",
  "content": "Today was productive!",
  "tags": ["daily", "reflection"]
}
```

---

## 📁 Project Structure

```
src/
├── main/
│   ├── java/com/example/journal/
│   │   ├── controller/
│   │   ├── model/
│   │   ├── repository/
│   │   ├── service/
│   │   ├── security/
│   │   └── config/
│   └── resources/
│       ├── application.properties
│       └── static/
└── test/
```

---

## 🛡️ License

This project is licensed under the **Apache 2.0 License**.  
See the [LICENSE](LICENSE) file for more information.

---

## 🚧 Future Enhancements

- 🌍 Full frontend integration (React, Angular, or Thymeleaf)
- 🌈 Sentiment analysis on entries
- 📊 Weekly writing analytics
- ☁️ Deployment on Render, AWS, or Heroku
- 🔊 Voice-to-text journal entries
- ✉️ Email summaries/reminders

---

## 🙌 Acknowledgments

- Spring Boot Team
- MongoDB Atlas
- External API Providers
- Java & Open Source Community
