# Blaze Diagnostics MVP Requirements

## Overview

Blaze Diagnostics is a workshop management platform designed to streamline vehicle repair workflows, improve communication between workshops and customers, and provide real-time job tracking from booking through completion.

The MVP focuses on core workshop operations including customer management, vehicle tracking, job cards, quotations, parts management, invoicing, and customer progress visibility.

---

# Epic 1: Authentication & Access Control

## User Story 1.1 – User Login

**As a workshop user**, I want to securely log in so that I can access the system and perform my role-specific tasks.

### Acceptance Criteria

* Users can log in using an email address and password.
* Invalid credentials display a clear error message.
* Successful login redirects users to the appropriate dashboard.
* User sessions are securely managed.
* Passwords are securely hashed and never stored in plain text.

---

## User Story 1.2 – Role-Based Access Control

**As a workshop owner**, I want users to have different access levels so that they only see information relevant to their responsibilities.

### Roles

* Workshop Admin
* Service Advisor
* Mechanic
* Customer
* System Admin (future enhancement)

### Acceptance Criteria

* Each user is assigned a role.
* Application routes are protected based on role permissions.
* Navigation menus display only relevant features.
* Unauthorized access attempts are blocked.

---

# Epic 2: Customer & Vehicle Management

## User Story 2.1 – Create Customer Profile

**As a service advisor**, I want to create and manage customer profiles so that jobs and vehicles are linked to the correct customer.

### Acceptance Criteria

* Customer records include:

  * Full Name
  * Phone Number
  * Email Address
  * Notes
* Customers can be searched and updated.
* A customer can own multiple vehicles.

---

## User Story 2.2 – Add Vehicle

**As a service advisor**, I want to add vehicles to customer profiles so that repair work can be accurately tracked.

### Acceptance Criteria

* Vehicle records include:

  * Make
  * Model
  * Year
  * Registration Number
  * VIN
  * Mileage
  * Notes
* Vehicles are linked to a customer profile.
* Vehicle information can be edited.

---

# Epic 3: Job Cards & Workflow Tracking

## User Story 3.1 – Create Job Card

**As a service advisor**, I want to create a job card so that work can be tracked throughout the repair process.

### Workflow Statuses

* Booked In
* Inspection Started
* Quote Required
* Awaiting Quote Approval
* Quote Approved
* Parts Ordered
* Awaiting Parts
* Parts Received
* In Progress
* Quality Check
* Ready for Collection
* Completed
* Cancelled

### Acceptance Criteria

* Job cards are linked to customers and vehicles.
* Job cards contain:

  * Status
  * Priority
  * Assigned Mechanic
  * Job Description
* Each job card has a unique reference number.

---

## User Story 3.2 – Update Job Status

**As a mechanic or service advisor**, I want to update job statuses so that workshop staff and customers remain informed.

### Acceptance Criteria

* Status updates are saved immediately.
* The user and timestamp are recorded.
* Customer-facing updates can be generated.
* Full status history is available.

---

# Epic 4: Quotes & Customer Approval

## User Story 4.1 – Create Quote

**As a service advisor**, I want to create a quote so that customers can approve repair costs before work proceeds.

### Acceptance Criteria

* Quotes are linked to job cards.
* Quotes support:

  * Parts
  * Labour
  * Quantities
  * Unit Costs
  * Totals
* Quotes can be saved as Draft or Sent for Approval.

---

## User Story 4.2 – Approve or Reject Quote

**As a customer**, I want to approve or reject a quote so that the workshop knows whether to continue with repairs.

### Acceptance Criteria

* Customers can approve quotes.
* Customers can reject quotes and provide an optional comment.
* Approval or rejection timestamps are recorded.
* Workshop staff can view quote status in real time.

---

# Epic 5: Parts Management

## User Story 5.1 – Track Parts

**As a service advisor**, I want to manage parts required for a repair so that ordering and installation progress can be monitored.

### Part Statuses

* Required
* Ordered
* Awaiting Delivery
* Delivered
* Installed
* Cancelled

### Acceptance Criteria

* Parts are linked to job cards.
* Part records include:

  * Name
  * Quantity
  * Supplier
  * Status
  * Expected Delivery Date
* Internal supplier costs are not visible to customers.

---

# Epic 6: Customer Progress Portal

## User Story 6.1 – View Vehicle Progress

**As a customer**, I want to track the progress of my vehicle online so that I can receive updates without contacting the workshop.

### Acceptance Criteria

* Customers can only view their own vehicles and jobs.
* Customers can see:

  * Current Job Status
  * Quote Status
  * Parts Progress
  * Ready-for-Collection Notifications
* Updates use clear, professional customer-facing language.

---

# Epic 7: Invoicing

## User Story 7.1 – Generate Invoice

**As a service advisor**, I want to generate invoices from approved work so that customers can be billed accurately.

### Acceptance Criteria

* Invoices are linked to:

  * Customer
  * Vehicle
  * Job Card
* Invoice statuses include:

  * Issued
  * Paid
* Approved quote items can be converted into invoice items.

---

# Epic 8: Activity Logging & Audit Trail

## User Story 8.1 – Track System Activity

**As a workshop admin**, I want important actions recorded so that there is accountability and traceability.

### Acceptance Criteria

The system logs:

* Job status changes
* Quote approvals and rejections
* Invoice creation
* User actions

Each log entry records:

* User
* Action Performed
* Date and Time

---

# Epic 9: Security & Data Protection

## User Story 9.1 – Secure Workshop Data

**As a workshop owner**, I want customer and workshop data protected so that confidential information remains secure.

### Acceptance Criteria

* Users can only access data they are authorized to view.
* Customers cannot access other customers' information.
* Sensitive configuration data is stored in environment variables.
* Security best practices are followed for authentication and authorization.
* System errors display user-friendly messages without exposing technical details.
* All data is transmitted over secure connections (HTTPS in production).
* Audit logs are maintained for critical actions.

---

# MVP Success Criteria

The MVP will be considered successful when:

* Workshop staff can manage customers, vehicles, jobs, quotes, parts, and invoices.
* Customers can monitor repair progress and approve quotations online.
* Role-based permissions are enforced across the platform.
* All critical actions are logged and traceable.
* Customer and workshop data remains secure and protected.
