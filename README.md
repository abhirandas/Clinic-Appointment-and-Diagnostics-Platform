🏥 Clinic Appointment and Diagnostics Platform

A comprehensive database design for managing a clinic's operations including patient appointments, consultations, diagnostics, and payments. This system is modeled using Crow’s Foot notation to clearly represent relationships between entities.

📌 Overview

This platform is designed to handle:

Patient registration and history tracking
Doctor and department management
Appointment scheduling and consultation workflow
Prescription handling
Diagnostic test ordering and reporting
Payment processing

It provides a complete end-to-end flow from booking an appointment to receiving diagnostic reports and making payments.

🧠 Database Design Approach
Notation Used: Crow’s Foot
Database Type: Relational Database
Focus: Normalized structure, scalability, and real-world healthcare workflow
🧩 Core Entities
🏢 Department & Specialization
DEPARTMENT → Stores hospital departments (e.g., Cardiology, Neurology)
SPECIALTY → Defines specific medical specialties under departments
👤 Patient Management
PATIENT
Stores personal, medical, and emergency details
Maintains patient history for future consultations
🩺 Doctor Management
DOCTOR
Linked to both Department and Specialty
Tracks availability status (Active, On Leave, etc.)
🏠 Room Management
ROOM
Represents clinic spaces (Consultation, Lab, Waiting, Private)
Tracks availability and usage status
📅 Appointment System
APPOINTMENT
Links Patient, Doctor, and Room
Tracks appointment lifecycle (Booked → Completed → Cancelled)
🩹 Consultation Workflow
CONSULTATION
Created after an appointment
Includes symptoms, diagnosis, notes, and follow-ups
💊 Prescription System
PRESCRIPTION
Linked to consultations
Stores medication details (dosage, frequency, duration)
🧪 Diagnostics & Lab
TEST_TYPE → Defines available tests
TEST_ORDER → Orders tests during consultation
LAB_TECHNICIAN → Handles test processing
REPORT → Stores test results and generated reports
💳 Payment System
PAYMENT
Linked to consultations
Supports multiple methods (UPI, Card, Insurance, etc.)
Tracks transaction status
🔗 Relationships (Crow’s Foot)
One-to-Many Relationships
One Department → Many Specialties, Doctors, Rooms, Technicians
One Specialty → Many Doctors
One Patient → Many Appointments, Consultations, Payments
One Doctor → Many Appointments & Consultations
One Room → Many Appointments & Consultations
One Appointment → One Consultation
One Consultation → Many Prescriptions, Test Orders, Payments
One Test Type → Many Test Orders
One Technician → Many Test Orders
One Test Order → One Report
🔄 Workflow
Patient registers in the system
Appointment is booked with a doctor
Consultation is conducted
Doctor may:
Prescribe medicines
Order diagnostic tests
Lab technician processes tests
Reports are generated
Payment is completed
⚙️ Features
✔️ Structured and normalized schema
✔️ Real-world healthcare workflow mapping
✔️ Clear separation of concerns (appointments vs consultations)
✔️ Scalable design for large clinics/hospitals
✔️ Supports diagnostics and billing in one system
🖼️ ER Diagram

Add your ER diagram image here

![ER Diagram](./er-diagram.png)
🚀 Future Improvements
Add User Authentication (Admin/Doctor/Patient roles)
Integrate Insurance Claims Processing
Add Inventory Management for Medicines
Implement Audit Logs & Data Security
Support Multi-branch Clinics
🧾 Notes
ENUM fields are used to maintain data consistency
Foreign keys enforce relational integrity
Timestamps help with auditing and tracking changes
🏁 Conclusion

This design models a realistic clinic management system with strong relational integrity and scalable architecture. It cleanly separates operational flows like appointments, consultations, diagnostics, and payments, making it suitable for production-level systems.
