# GTN Engineering IT Helpdesk System

A comprehensive IT helpdesk system built with Flask and SQLite, featuring role-based access control and automated user system information capture.

## Features

- **Role-Based Access Control**: Super Admin, Admin, and User roles
- **Automatic System Detection**: Captures user IP address and system name
- **Category-Based Assignment**: Hardware and Software specialist admins
- **Complete Ticket Management**: Create, assign, track, and resolve tickets
- **User Profile Management**: Profile updates with image upload capability
- **Comprehensive Dashboards**: Different views for each role type

## Database Schema

The system uses SQLite with three main tables:

### Users Table
- User authentication and profile information
- Role management (user, admin, super_admin)
- System information tracking (IP address, system name)

### Tickets Table
- Complete ticket information
- User system data captured at creation time
- Assignment and status tracking

### Ticket Comments Table
- Comment system for ticket updates
- User interaction tracking

## Installation & Setup

1. **Prerequisites**
   ```bash
   pip install flask flask-sqlalchemy flask-wtf flask-login werkzeug
   ```

2. **Database Setup**
   ```bash
   python export_to_sqlite.py
   ```

3. **Run Application**
   ```bash
   python main.py
   ```

## User Accounts

### Super Admin
- **Username**: superadmin
- **Password**: super123
- **Capabilities**: Full system access, user management, work assignment

### Hardware Admins
- **Usernames**: yuvaraj, jayachandran, narainkarthik
- **Password**: admin123
- **Department**: IT Hardware

### Software Admins
- **Usernames**: sathish, lakshmiprabha
- **Password**: admin123
- **Department**: IT Software

### Test User
- **Username**: testuser
- **Password**: test123
- **Role**: Regular user

## System Workflow

1. **User Creates Ticket**: System captures IP address and system name
2. **Super Admin Reviews**: Views all tickets with user system information
3. **Work Assignment**: Super Admin assigns to category-specific admins
4. **Admin Resolution**: Assigned admin works on and resolves tickets
5. **Status Updates**: Users receive notifications on ticket progress

## File Structure

```
gtn-helpdesk/
├── app.py              # Flask application configuration
├── main.py             # Application entry point
├── models.py           # Database models
├── routes.py           # Application routes
├── forms.py            # WTForms definitions
├── export_to_sqlite.py # Database setup script
├── gtn_helpdesk.db     # SQLite database file
├── static/
│   ├── style.css       # Custom styling
│   └── script.js       # Client-side functionality
└── templates/          # HTML templates
    ├── base.html
    ├── index.html
    ├── user_*.html
    ├── admin_*.html
    └── super_admin_*.html
```

## Key Features Implemented

- **System Information Capture**: Automatic detection of user IP and system name
- **Category-Based Assignment**: Hardware/Software admin specialization
- **Enhanced Dashboards**: Role-specific views with comprehensive statistics
- **User Management**: Super Admin can create and manage all users
- **Profile Management**: Users can update their profiles and upload images
- **Complete Audit Trail**: All ticket activities tracked with timestamps

## Security Features

- Password hashing using Werkzeug security
- Session-based authentication
- Role-based access control
- SQL injection protection through SQLAlchemy ORM

## Technical Stack

- **Backend**: Python Flask
- **Database**: SQLite
- **Frontend**: Bootstrap 5, Remix Icons
- **Forms**: Flask-WTF
- **Authentication**: Flask-Login
- **ORM**: SQLAlchemy

## Development Notes

The application is designed for local deployment with SQLite for easy setup and maintenance. All user system information is captured automatically when tickets are created, providing comprehensive tracking for IT support operations.