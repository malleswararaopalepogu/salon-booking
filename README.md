# 💇 Salon Booking System

A full-stack **Salon Booking System** that allows customers to browse salon services, create accounts, book appointments, and manage their bookings. Salon owners can manage their salon services, availability, and customer appointments through the application.

The project is designed to demonstrate **full-stack application development, REST API development, authentication, database integration, and real-world booking workflows**.

---

## 🚀 Features

### 👤 Customer Features

- User registration and login
- Secure authentication
- Browse available salon services
- View service details
- Select date and time for appointments
- Book salon appointments
- View booking history
- Manage existing bookings
- Cancel appointments
- User profile management

### 💇 Salon Management

- Manage salon services
- Add and update services
- Manage service availability
- View customer appointments
- Manage appointment status
- Maintain salon information

### 🔐 Authentication & Security

- User authentication
- JWT-based authentication
- Password encryption using BCrypt
- Protected REST APIs
- Role-based authorization
- Authentication filters
- Secure API communication

---

## 🛠️ Tech Stack

### Backend

- **Java**
- **Spring Boot**
- **Spring Security**
- **Spring Data JPA**
- **REST APIs**
- **JWT**
- **Maven**

### Frontend

- **React.js**
- **JavaScript**
- **HTML5**
- **CSS3**
- **Axios**

### Database

- **MySQL**

### Development Tools

- **Git**
- **GitHub**
- **Postman**
- **Eclipse**
- **VS Code**
- **MySQL Workbench**

---

## 🏗️ Architecture

The application follows a layered architecture:

```text
                    ┌─────────────────────┐
                    │      React UI       │
                    │    Frontend Layer   │
                    └──────────┬──────────┘
                               │
                               │ HTTP / REST API
                               ▼
                    ┌─────────────────────┐
                    │    Spring Boot      │
                    │   REST Controllers  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │    Service Layer    │
                    │ Business Logic      │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Repository Layer  │
                    │    Spring Data JPA  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │       MySQL         │
                    │      Database       │
                    └─────────────────────┘
```

---

## 📂 Project Structure

```text
salon-booking/
│
├── salon booking project source code/
│
│   ├── backend/
│   │   ├── src/
│   │   │   ├── main/
│   │   │   │   ├── java/
│   │   │   │   │   └── ...
│   │   │   │   └── resources/
│   │   │   │       └── application.properties
│   │   │   │
│   │   │   └── test/
│   │   │
│   │   └── pom.xml
│   │
│   └── frontend/
│       ├── src/
│       ├── public/
│       ├── package.json
│       └── ...
│
├── .gitignore
├── package-lock.json
└── README.md
```

> Update the folder structure above if your actual backend/frontend folder names are different.

---

## 🔐 Authentication Flow

The application uses **JWT-based authentication**.

```text
User
 │
 │ Login
 ▼
React Frontend
 │
 │ POST /login
 ▼
Spring Boot
 │
 │ Authenticate credentials
 ▼
Spring Security
 │
 │ Validate username/password
 ▼
JWT Token Generated
 │
 ▼
Frontend
 │
 │ Sends JWT with protected requests
 ▼
JWT Request Filter
 │
 │ Validate token
 ▼
Spring Security Context
 │
 ▼
Protected Controller
```

### Security Components

The backend uses:

- Spring Security
- JWT
- BCrypt Password Encoder
- AuthenticationManager
- AuthenticationProvider
- JWT Request Filter
- SecurityFilterChain
- Role-based authorization

---

## 📅 Booking Flow

The basic booking workflow is:

```text
Customer
   │
   ▼
Login / Register
   │
   ▼
Browse Services
   │
   ▼
Select Service
   │
   ▼
Select Date & Time
   │
   ▼
Create Booking
   │
   ▼
Booking Stored in Database
   │
   ▼
Salon Owner Manages Booking
   │
   ▼
Booking Status Updated
```

---

## 🗄️ Database

The application uses **MySQL** as the relational database.

Major entities include:

- User
- Salon
- Service
- Booking
- Appointment-related data

The application uses **Spring Data JPA** to communicate with the database.

Example relationship:

```text
User
 │
 ├───────────────┐
 │               │
 ▼               ▼
Bookings       Profile
 │
 ▼
Service
 │
 ▼
Salon
```

---

## 🔌 REST API

The backend exposes REST APIs that are consumed by the React frontend.

Typical API operations include:

### Authentication

```text
POST   /register
POST   /login
POST   /logout
GET    /is-authenticated
```

### User

```text
GET    /profile
PUT    /profile
```

### Booking

```text
POST   /bookings
GET    /bookings
GET    /bookings/{id}
PUT    /bookings/{id}
DELETE /bookings/{id}
```

> API paths may vary depending on the current implementation.

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/malleswararaopalepogu/salon-booking.git
```

```bash
cd salon-booking
```

---

### 2. Backend Setup

Open the backend project in **Eclipse** or your preferred IDE.

Configure the MySQL database in:

```text
application.properties
```

Example:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/salon_booking
spring.datasource.username=root
spring.datasource.password=YOUR_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

Then run the Spring Boot application.

---

### 3. Frontend Setup

Navigate to the frontend directory:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The frontend will normally be available at:

```text
http://localhost:5173
```

---

## 🧪 API Testing

The REST APIs can be tested using **Postman**.

Example authentication flow:

```text
1. Register User
       ↓
2. Login
       ↓
3. Receive JWT
       ↓
4. Send JWT with protected requests
       ↓
5. Access Profile / Booking APIs
```

---

## 🔒 Security

Security is implemented using **Spring Security and JWT**.

Important security practices used in the project:

- Passwords are stored using BCrypt hashing
- Protected endpoints require authentication
- JWT is validated before accessing protected resources
- Stateless authentication is used
- CORS is configured for frontend-backend communication
- Role-based access can be applied to protected endpoints

---

## 🎯 Key Learning Outcomes

Through this project, I gained practical experience in:

- Building RESTful APIs using Spring Boot
- Implementing authentication using Spring Security
- Understanding JWT authentication
- Implementing JWT request filters
- Working with Spring Data JPA
- Designing relational database entities
- Connecting React with Spring Boot
- Using Axios for API communication
- Implementing CRUD operations
- Handling authentication state in React
- Testing APIs using Postman
- Using Git and GitHub for version control

---

## 🔮 Future Enhancements

Possible future improvements include:

- Online payment integration
- Email/SMS booking notifications
- Appointment reminders
- Advanced search and filtering
- Salon reviews and ratings
- Admin dashboard
- Multiple salon support
- Docker containerization
- Cloud deployment
- Microservices architecture
- Redis caching
- API documentation using Swagger/OpenAPI

---

## 📌 Project Highlights

> **Full-Stack Salon Booking Application** built using **Spring Boot, Spring Security, JWT, React, Spring Data JPA, and MySQL**.

The project demonstrates the complete flow from **frontend interaction → REST API → authentication/security → business logic → database persistence**.

---

## 👨‍💻 Developer

**PALEPOGU NAGAMALLESWARARAO**

Java | Spring Boot | React | MySQL | REST APIs

### GitHub

[Salon Booking Repository](https://github.com/malleswararaopalepogu/salon-booking?utm_source=chatgpt.com)

---

## ⭐ If you find this project useful

Feel free to explore the source code and provide feedback.
