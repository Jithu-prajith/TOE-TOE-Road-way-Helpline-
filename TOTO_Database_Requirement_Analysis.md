# Database Requirement Analysis for TOTO  
## Smart Roadside Assistance Platform

---

# 1. Introduction

The database for TOTO is designed to manage roadside assistance services efficiently.  
It stores user information, mechanic details, emergency requests, service tracking, and system management data.

The database should support:
- Fast access to emergency requests
- Real-time service updates
- Secure user authentication
- Mechanic availability tracking
- Location-based service matching

---

# 2. Objectives of Database System

The database system aims to:

- Store user and mechanic information securely
- Manage roadside assistance requests
- Track service request status
- Support location-based mechanic matching
- Maintain service history records

---

# 3. Functional Requirements

## 3.1 User Management
The system should:
- Register users
- Authenticate users
- Store profile details
- Manage vehicle information

### User Data Includes:
- User ID
- Name
- Email
- Phone Number
- Password
- Vehicle Details
- Address

---

## 3.2 Mechanic Management
The system should:
- Register mechanics
- Verify mechanic accounts
- Track mechanic availability
- Store service specialization

### Mechanic Data Includes:
- Mechanic ID
- Name
- Contact Information
- Garage Name
- Location
- Availability Status
- Experience
- Services Offered

---

## 3.3 Service Request Management
The system should:
- Allow users to create emergency requests
- Assign requests to nearby mechanics
- Track request progress

### Request Data Includes:
- Request ID
- User ID
- Mechanic ID
- Issue Type
- Current Location
- Date & Time
- Request Status

---

## 3.4 Service Tracking
The system should:
- Track request status in real-time
- Update service completion status
- Maintain request history

### Status Types:
- Pending
- Accepted
- In Progress
- Completed
- Cancelled

---

## 3.5 Admin Management
The admin should:
- Monitor users
- Verify mechanics
- Manage requests
- Handle complaints

### Admin Data Includes:
- Admin ID
- Username
- Password
- Role

---

# 4. Non-Functional Requirements

## 4.1 Security
- Password encryption
- Secure authentication
- Data privacy protection

## 4.2 Scalability
- Support increasing users and requests
- Efficient database performance

## 4.3 Reliability
- Data backup support
- High availability

## 4.4 Performance
- Fast query response
- Efficient request handling

---

# 5. Database Entities

## Main Entities

### 1. User
Stores customer information.

### 2. Mechanic
Stores mechanic/service provider details.

### 3. Service Request
Stores roadside assistance requests.

### 4. Admin
Stores administrator information.

### 5. Service History
Stores completed request records.

### 6. Vehicle
Stores vehicle details of users.

---

# 6. Entity Relationships

| Entity 1 | Relationship | Entity 2 |
|----------|--------------|----------|
| User | Creates | Service Request |
| Mechanic | Handles | Service Request |
| User | Owns | Vehicle |
| Admin | Monitors | Users |
| Admin | Verifies | Mechanics |
| Service Request | Generates | Service History |

---

# 7. Suggested Database Tables

## Users Table
| Field Name | Data Type |
|------------|-----------|
| user_id | INT |
| name | VARCHAR |
| email | VARCHAR |
| phone | VARCHAR |
| password | VARCHAR |
| address | TEXT |

---

## Mechanics Table
| Field Name | Data Type |
|------------|-----------|
| mechanic_id | INT |
| name | VARCHAR |
| phone | VARCHAR |
| location | VARCHAR |
| experience | INT |
| availability | BOOLEAN |

---

## Vehicles Table
| Field Name | Data Type |
|------------|-----------|
| vehicle_id | INT |
| user_id | INT |
| vehicle_type | VARCHAR |
| vehicle_model | VARCHAR |
| registration_number | VARCHAR |

---

## Service Requests Table
| Field Name | Data Type |
|------------|-----------|
| request_id | INT |
| user_id | INT |
| mechanic_id | INT |
| issue_type | VARCHAR |
| status | VARCHAR |
| request_time | DATETIME |
| location | TEXT |

---

## Admin Table
| Field Name | Data Type |
|------------|-----------|
| admin_id | INT |
| username | VARCHAR |
| password | VARCHAR |

---

# 8. Database Constraints

- Primary keys for all tables
- Foreign key relationships
- Unique email and phone numbers
- NOT NULL constraints for important fields

---

# 9. Recommended Database

## MongoDB
Recommended because:
- Flexible schema
- Easy scalability
- Good support for location-based queries
- Suitable for real-time applications

Alternative:
- MySQL
- PostgreSQL

---

# 10. Future Database Enhancements

- GPS tracking support
- Payment integration tables
- AI-based mechanic recommendation
- Live notification system
- Review and rating system

---

# 11. Conclusion

The TOTO database system is designed to efficiently manage roadside assistance operations by handling users, mechanics, service requests, and real-time service tracking.

The database ensures:
- Fast emergency handling
- Secure data management
- Scalable architecture
- Reliable roadside assistance support
