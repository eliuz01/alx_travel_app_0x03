# alx_travel_app

**ALX Travel – Django REST API (Airbnb Clone)**

Backend system built for managing listings, bookings, authentication, and asynchronous notifications. Designed for secure, scalable, high-performance operations using Django REST Framework and Celery.

**Core Features**

***Secure Authentication & Custom User Workflows***
Email-based registration and login
JWT/session authentication
Users manage personal bookings and reviews
Separation of Host vs Guest permissions

***Product (Listing) & Inventory (Availability) Management***
Hosts create listings with title, description, price, and location
Real-time booking availability
Automatically tracks created and booked dates

***Cart & Order Processing (Bookings System)***
Guests book listings with selected check-in/check-out dates
Multi-day pricing and snapshot pricing
View, edit, or cancel reservations

***Payment & Status Automation***
Workflow: Pending → Paid → Confirmed → Completed → Cancelled
Integrates easily with Stripe, PayPal, or M-Pesa APIs
Transaction-aware email notifications

***Scalable, High-Performance Architecture***
Caching for repeated listing retrieval
Celery + Redis for async tasks (booking confirmation emails)
Optimized queries and pagination support

***Tech Stack***
Technology	Purpose
Django	Core backend
Django REST Framework	APIs & serialization
Celery	Async email sending
Redis	Background task broker
PostgreSQL	Production-ready DB
JWT Auth / Session	Secure authentication
Docker (Optional)	Deployment scaling

***Models Overview***
Model	Purpose
Listing	Represents accommodation properties
Booking	Links guest → listing with date ranges
Review	Rating & comment system for listings

Example: /models.py includes Listing, Booking, Review

**API Endpoints (Sample)**
Method	Endpoint	Description
GET	/api/listings/	Get all listings
POST	/api/listings/	Host creates a listing
POST	/api/bookings/	Guest books a listing
GET	/api/bookings/	View bookings
POST	/api/reviews/	Add listing review
✉ Async Email Example

Booking confirmation handled via Celery task:

send_booking_confirmation.delay(email, booking_details)


ALX ProDev Backend Engineering Final Project
