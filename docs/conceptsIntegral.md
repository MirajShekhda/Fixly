# Fixly Project – Key Concepts

This file explains the important ideas behind the **Fixly** service marketplace. Concepts are grouped into three types: **Objects**, **Contexts**, and **Information**.

---

## Objects (Main Parts of the System)

### User
- *Context*: Login and account management
- *Information*:
  - Stores user details (ID, name, email, phone)
  - Holds password and login tokens
  - Defines type: customer, provider, or admin
  - Has profile image and short bio

### Service Provider
- *Context*: Managing services they offer
- *Information*:
  - Special type of user
  - Has verification status
  - Lists services offered and available time
  - Includes payment info
  - Shows ratings and earnings

### Service Category
- *Context*: Organizing services into groups
- *Information*:
  - Name and details of the category
  - Image for display
  - Can be a parent or subcategory
  - Shows whether it’s active

### Service Listing
- *Context*: Service details shown to customers
- *Information*:
  - Title, description, price
  - Linked to provider and category
  - Includes photos
  - Calculates commission and income

### Booking
- *Context*: When a customer books a service
- *Information*:
  - Connects customer, provider, and listing
  - Stores date and time
  - Status (Pending, Confirmed, Done, Cancelled)
  - Payment details and notes

### Payment
- *Context*: Handling money for bookings
- *Information*:
  - Booking-related payment info
  - Payment type (UPI, card), status, ID
  - Total amount and share for provider/platform

### Commission
- *Context*: Platform’s share from bookings
- *Information*:
  - Linked to bookings and provider
  - Shows percentage and total
  - Tracks when it was collected

### Admin Earnings
- *Context*: Total money earned by platform
- *Information*:
  - Daily income summary
  - Total commission and bookings
  - Linked to all commissions

### Review
- *Context*: Customer feedback
- *Information*:
  - Rating and text review
  - Linked to customer and booking
  - Affects provider rating

### Complaint
- *Context*: Handling customer issues
- *Information*:
  - Customer complaints about service
  - Status (Open, Reviewed, Solved, Closed)
  - Notes from admin

### Report
- *Context*: Admin reports and summaries
- *Information*:
  - Report types (Earnings, Bookings, etc.)
  - Time period and stats
  - Financial data

---

## Contexts (Where the Objects Are Used)

### Login & Account Context
- *Objects*: User
- *Information*:
  - Login and signup system using JWT
  - Password reset and security features

### Provider Context
- *Objects*: Service Provider, Listing
- *Information*:
  - Signup and verification
  - Create/edit services
  - Handle bookings and see earnings

### Customer Context
- *Objects*: User, Booking, Review, Complaint
- *Information*:
  - Search and view services
  - Book and pay for services
  - Leave ratings and file complaints

### Admin Context
- *Objects*: Admin, Report, Complaint
- *Information*:
  - Manage users and providers
  - Resolve complaints
  - Create reports and monitor activity

### Payment Context
- *Objects*: Payment, Commission, Admin Earnings
- *Information*:
  - Record payments
  - Calculate and collect commission
  - Track platform income

---
## Workflows

### Provider Signup & Verification
- Provider applies to join
- Admin checks and verifies
- Only verified providers can list services

### Booking Steps
1. Customer books a service (Pending)
2. Provider accepts or rejects
3. Service is done
4. Customer marks as completed
5. Payment is processed
6. Customer can give review

### Review Process
- Only completed bookings can be reviewed
- Reviews affect provider ratings
- Provider rating = average of all reviews

### Commission Rules
- Platform takes 10% from bookings (default)
- Rate can change (0–30%)
- Collected after booking is completed


