# Airbnb Clone Project

## Overview

The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. This project aims to strengthen full-stack development skills by focusing on backend systems, database architecture, API development, and secure deployment. 

## Project Goals

- Develop a deep understanding of backend architecture and secure API development.
- Gain hands-on experience with modern technologies such as Django, MySQL, and GraphQL.
- Learn to manage development pipelines using CI/CD tools.
- Collaborate effectively in a simulated professional development team.
- Document all aspects of the project using Markdown and GitHub.

## Technology Stack

### Django
A high-level Python web framework that simplifies backend development and supports rapid, secure development of RESTful APIs.

### MySQL
A reliable, open-source relational database system used for storing and managing structured application data.

### GraphQL
A query language that enables clients to request specific data, improving the efficiency and flexibility of API communication.

### Docker
Used to containerize the application, ensuring consistency across development, testing, and production environments.

### GitHub Actions
An automation tool for continuous integration and deployment workflows, enabling automatic testing and deployment of code changes.



## Team Roles

### Backend Developer
Responsible for designing, developing, and maintaining the server-side logic, APIs, and business logic using Django and GraphQL.

### Database Administrator
Designs and manages the relational database schema, ensures data integrity, optimizes performance, and manages migrations using MySQL.

### DevOps Engineer
Implements and maintains CI/CD pipelines, containerization, and deployment processes using Docker and GitHub Actions.

### Security Engineer
Ensures all APIs are secure by implementing proper authentication, authorization, and data protection strategies.

### Technical Writer / Documenter
Maintains comprehensive documentation for the codebase, setup guides, database schema, and API endpoints in Markdown format.



## Database Design

The Airbnb Clone project uses a relational database structure designed for clarity, scalability, and performance. The primary entities and their relationships are listed below.

### Users
- `user_id` (Primary Key)
- `name`
- `email`
- `password_hash`
- `account_created_at`

### Properties
- `property_id` (Primary Key)
- `owner_id` (Foreign Key to Users)
- `title`
- `description`
- `location`

### Bookings
- `booking_id` (Primary Key)
- `property_id` (Foreign Key to Properties)
- `user_id` (Foreign Key to Users)
- `start_date`
- `end_date`

### Reviews
- `review_id` (Primary Key)
- `booking_id` (Foreign Key to Bookings)
- `user_id` (Foreign Key to Users)
- `rating`
- `comment`

### Payments
- `payment_id` (Primary Key)
- `booking_id` (Foreign Key to Bookings)
- `amount`
- `payment_method`
- `payment_status`

### Entity Relationships
- A user can create multiple properties.
- A user can make multiple bookings for different properties.
- A booking belongs to a property and is made by a user.
- A review is written by a user about a booking.
- A payment is associated with a specific booking.

---

## Feature Breakdown

### User Management
Allows users to register, log in, update their profile, and manage their account securely. Authentication and session management are handled by Django with hashed passwords and token-based access.

### Property Management
Property owners can list, update, and remove their properties. Each listing includes a title, description, images, pricing, and availability.

### Booking System
Users can search available properties and make bookings for specific dates. The booking system ensures that date conflicts are avoided.

### Review System
After completing a booking, users can leave a review including a star rating and comment. Reviews are linked to specific bookings.

### Payment Processing
Simulates secure payment processing for bookings. Includes payment status updates and logging transaction metadata for record-keeping.



## API Security

### Authentication
Only authenticated users can access protected endpoints. This will be handled via JWT tokens or Django’s built-in authentication system.

Why it matters: Ensures that only registered users can perform actions like booking or reviewing properties.

### Authorization
Users are authorized based on their role (e.g., guest vs. property owner). This prevents unauthorized access to resources they don’t own.

Why it matters: Prevents users from modifying other users’ properties or bookings.

### Rate Limiting
Limits the number of API requests per user to prevent abuse or DDoS attacks.

Why it matters: Protects server resources and ensures fair usage across all users.

### Input Validation and Sanitization
All user inputs are validated and sanitized to prevent SQL injection, XSS, and other attack vectors.

Why it matters: Protects the integrity and security of both user data and backend systems.



## CI/CD Pipeline

### What is CI/CD?
CI/CD (Continuous Integration / Continuous Deployment) is a method to automate software building, testing, and deployment. It helps ensure that code changes are integrated and delivered quickly and reliably.

### Why It’s Important
- Ensures rapid, consistent deployment with fewer errors.
- Automatically tests code before merging, catching bugs early.
- Makes collaboration seamless with frequent integration of features.

### Tools Used
- GitHub Actions: Automates testing and deployment workflows every time code is pushed to the repository.
- Docker: Ensures consistent environments across development, staging, and production.
- Optional Tools: Heroku or Render for deployment; Postman/Newman for automated API testing.


