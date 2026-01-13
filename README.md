Restaurant Reservation Management System

A full-stack web application built using Python, Django, HTML, CSS, and SQLite that enables customers to reserve tables online and allows administrators to manage restaurant reservations efficiently through role-based access control.

Live Demo:https://restaurant-management-k1qt.onrender.com/

=>Tech Stack:-
Backend: Python, Django (MVT Architecture)
Frontend: HTML, CSS, Django Templates
Database: SQLite
Authentication: Django built-in authentication system
Deployment: Render

=>Setup Instructions (Local Development):-
Follow these steps to run the project locally:
1️)Clone the Repository
git clone https://github.com/Komalchowdary25/Restaurant_Management.git
cd Restaurant_Management
2️)Create & Activate Virtual Environment
python -m venv myenv
myenv\Scripts\activate   # Windows
# source myenv/bin/activate   # Mac/Linux
3️)Install Dependencies
pip install -r requirements.txt
4️)Apply Migrations
python manage.py migrate
5️)Create Superuser (Admin)
python manage.py createsuperuser
6️)Run Development Server
python manage.py runserver

**Demo Credentials:-
Use the following credentials to access the application:

👤 Admin User
Username: admin123
Password: admin@565

👤 Customer User
Username: user1
Password: user@565

=>User Roles & Access Control:-
The system supports two roles using Django’s authentication and authorization system:
1)Customer (Regular User)
Can log in and book table reservations
Can view their own reservations
Can cancel their reservations
Cannot access admin pages or other users’ data

2)Admin (Staff User)
Can view all reservations
Can filter reservations by date
Can modify reservation details (date, time, guests)
Can cancel any reservation
Has access to Django Admin Panel

=>Role distinction is implemented using:
i)is_authenticated
ii)is_staff
iii)Django decorators like @login_required and @staff_member_required

=>Reservation & Availability Logic:-
User submits:
i)Reservation date
ii)Time slot
iii)Number of guests

System checks:
i)Available tables with capacity ≥ guest count
ii)Table availability for the selected date and time

If a suitable table is available:
i)Reservation is created
ii)Table is marked as reserved for that slot

If no table is available:
i)User receives a validation message

On cancellation:
i)Reservation is removed
ii)Table becomes available again

This ensures:
i)No double booking
ii)Capacity-based table allocation
iii)Accurate availability management

=>Assumptions Made:-
A table can be reserved for only one reservation per date & time slot
Time slots are assumed to be fixed (no partial overlaps)
SQLite is sufficient for demo and evaluation purposes
Admin users are created via Django Admin Panel
Payment processing is out of scope

=>Known Limitations
No real-time availability updates (requires page refresh)
No email or SMS notifications
SQLite database (not ideal for large-scale production)
No table grouping for very large parties
Limited mobile responsiveness (basic support only)

=>Areas for Improvement (With More Time)
Integrate PostgreSQL for production-ready database
Add email confirmation and cancellation notifications
Implement time-slot overlap handling
Improve mobile UI responsiveness
Add analytics dashboard for admin
Enable user registration with email verification
Introduce REST APIs for frontend/mobile clients

Author:-
Komal Chowdary
Associate Software Engineer | Full-Stack Developer
Email:- komalchowdary25@gmail.com
GitHub: https://github.com/Komalchowdary25
