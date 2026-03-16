# VenueBook Auditorium Booking App Architecture Document

**Date:** 2026-03-16  
**Created by:** sinannkhalid-jpg

---

### 1. System Design Overview
The VenueBook auditorium booking app is designed to facilitate the booking of auditoriums for various events. The system will enable users to search for available auditoriums, book slots for events, manage bookings, and provide administrative features for venue owners.

### 2. Tech Stack
- **Frontend:**  
  - React.js  
  - Redux for state management  
  - Bootstrap for UI components  
- **Backend:**  
  - Node.js with Express  
  - JWT for authentication  
- **Database:**  
  - MongoDB for storing user data, bookings, and auditorium information  
- **Deployment:**  
  - Docker for containerization  
  - Hosting on AWS or Heroku

### 3. Database Schema
**User**  
- `userID`: ObjectID   
- `username`: String  
- `email`: String  
- `password`: String (hashed)  
- `role`: String (User or Admin)

**Auditorium**  
- `auditoriumID`: ObjectID   
- `name`: String  
- `location`: String  
- `capacity`: Number  
- `facilities`: Array of Strings

**Booking**  
- `bookingID`: ObjectID   
- `userID`: ObjectID (reference to User)  
- `auditoriumID`: ObjectID (reference to Auditorium)  
- `startTime`: Date  
- `endTime`: Date  
- `status`: String (Confirmed, Cancelled)

### 4. API Endpoints
- **User Management**  
  - `POST /api/users/register`: Register a new user  
  - `POST /api/users/login`: User login  
  - `GET /api/users/:id`: Get user details  
  
- **Auditorium Management**  
  - `GET /api/auditoriums`: List all auditoriums  
  - `POST /api/auditoriums`: Add a new auditorium (Admin)  
  - `PUT /api/auditoriums/:id`: Update auditorium details (Admin)  
  - `DELETE /api/auditoriums/:id`: Delete an auditorium (Admin)  
  
- **Booking Management**  
  - `POST /api/bookings`: Create a new booking  
  - `GET /api/bookings/:id`: Get booking details  
  - `PUT /api/bookings/:id`: Update booking details  
  - `DELETE /api/bookings/:id`: Cancel a booking

### 5. Feature Roadmap
- **Phase 1: Core Features**  
  - User authentication (sign up, log in, role management)  
  - Auditorium listing and search functionality  
  - Basic booking system

- **Phase 2: Enhanced Features**  
  - User account management  
  - Booking history and management  
  - Notifications for booking status

- **Phase 3: Administrative Features**  
  - Dashboard for auditorium owners  
  - Analytics for usage and booking statistics  
  - Payment integration
