# Movie-booking_19
UI 
Create a responsive frontend for a Movie Ticket Booking System.

Pages required:

1. Home Page (movies + search)
2. Movie Listing Page
3. Theater Selection Page
4. Show Timing Page
5. Seat Selection Page (visual layout with selectable seats)
6. Booking Summary Page
7. Payment Page (dummy)
8. Ticket Confirmation Page
9. Login/Register Page
10. Admin Dashboard
11. Manager Dashboard

UI Requirements:

- Use modern UI with cards, gradients, and icons
- Seat layout should visually show available, booked, and selected seats
- Color codes:
  - Green: available
  - Red: booked
  - Blue: selected
- Include navbar with search (movie, city, date)
- Mobile responsive design
- Use CSS animations and hover effects

Functional Requirements:

- Fetch data using REST APIs
- Dynamic seat selection
- Show total price calculation
- Form validation

Tech:

- HTML, CSS, JavaScript (or React if needed)
- Use fetch/axios for API calls
  Build backend APIs for a Movie Ticket Booking System using Spring Boot and JdbcTemplate (no JPA).

Architecture:

- Controller Layer
- Service Layer
- DAO Layer
- Model Layer

Modules:

1. Authentication (Admin, Manager, User)
2. Cinema Management
3. Movie Management
4. Show Management
5. Seat Management
6. Booking System
7. Subscription & Email Service

Key APIs:

Auth:

- POST /register
- POST /login

Movies:

- GET /movies
- POST /movies (admin)
- GET /movies/{id}

Theaters:

- GET /theaters
- POST /theaters

Shows:

- GET /shows?movieId=&date=
- POST /shows

Seats:

- GET /seats?showId=
- POST /seats/block

Booking:

- POST /booking
- GET /booking/{userId}

Subscription:

- POST /subscribe
- GET /notify-users

Rules:

- Only 50% seats available online
- Prevent double booking (use locking logic)
- Calculate total cost including delivery charges

Email:

- Send confirmation email with:
  - Movie name
  - Seat numbers
  - Time
  - Theater

Other:

- Exception handling
- Input validation
- Use DTOs
  Design MySQL database schema for a Movie Ticket Booking System.

Tables:

Users:

- user_id (PK)
- name
- email
- password
- role (ADMIN, MANAGER, USER)

Cinema_Halls:

- hall_id (PK)
- name
- type (multiplex/single)
- location
- facilities
- map_url

Screens:

- screen_id (PK)
- hall_id (FK)
- seating_capacity

Movies:

- movie_id (PK)
- title
- genre
- duration
- release_date

Shows:

- show_id (PK)
- movie_id (FK)
- screen_id (FK)
- show_time
- price

Seats:

- seat_id (PK)
- screen_id (FK)
- seat_number
- class (Silver, Gold, Platinum)

Bookings:

- booking_id (PK)
- user_id (FK)
- show_id (FK)
- total_amount
- booking_time

Booking_Seats:

- id (PK)
- booking_id (FK)
- seat_id (FK)

Subscriptions:

- id (PK)
- user_id (FK)
- movie_id (FK)

Constraints:

- Only 50% seats available online
- Unique constraint on (show_id + seat_id)

Also:

- Insert sample data
- Add indexes for performance

  Enhance Movie Booking System with advanced features:

- Seat locking mechanism (timeout 5 mins)
- Payment gateway simulation
- QR code ticket generation
- Email + SMS notification
- Movie recommendation system
- Admin analytics dashboard (bookings, revenue)
- Caching (Redis optional)
- Load handling (multiple users booking same show)
I have a Movie Ticket Booking System project based on Java & MySQL.

Refer to the system:

- Users: Admin, Manager, User
- Features:
  - Registration/Login
  - Theater & Movie management
  - Seat selection & booking
  - Payment & confirmation
  - Subscription system

(Reference: UML diagrams, activity diagram, and pages 0)

---

### 🔁 SYSTEM FLOW (IMPORTANT)

Generate the full flow step-by-step:

1. User visits website
2. User registers or logs in
3. System validates credentials
4. Based on role:
   - Admin → Manage managers
   - Manager → Add theater, screens, timings, movies
   - User → Browse movies

5. User Flow:
   - Select movie
   - Select theater & show
   - View available seats
   - Select seats
   - Proceed to payment
   - Booking confirmed
   - Email sent

6. Manager Flow:
   - Login
   - Add theater
   - Add screen timings
   - Add seats
   - Add movies

7. Admin Flow:
   - Login
   - Add/remove managers
   - Monitor system

8. Logout

---

### 🧠 ARCHITECTURE FLOW

Explain request flow:

User → Frontend → Controller → Service → DAO → Database  
Database → DAO → Service → Controller → Frontend

---

### 🎯 FRONTEND
- HTML/CSS/JS (or React)
- Pages:
  - Login/Register
  - Home
  - Movie Selection
  - Seat Selection
  - Booking Confirmation
  - Admin/Manager Dashboard

---

### ⚙️ BACKEND
- Java (Spring Boot, no JPA)
- Layers:
  - Controller
  - Service
  - DAO (JDBC)

---

### 🗄️ DATABASE
Tables:
- Users
- Managers
- Movies
- Theaters
- Screens
- Seats
- Bookings

---

### 📦 OUTPUT
- Folder structure (frontend + backend)
- APIs
- Sample code
- SQL schema

---

### 🚀 EXTRA
- Seat locking logic
- JWT auth
- Email service

Generate everything clearly.
