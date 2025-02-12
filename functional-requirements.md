# Functional Requirements Document

## 1. User Management
- Users should be able to register and log in.
- Role-based access control:
    - **Librarian**: Admin-level access to manage books and users.
    - **Member**: Regular users who can borrow/return books.
- User profile management:
    - Update name, contact details, password.

## 2. Book Management
Librarians should be able to:
- Add new books to the system.
- Update book details (title, author, category, etc.).
- Remove books from the catalog.

Each book should have:
- **Title, Author, ISBN, Category, Published Year**
- **Number of available copies**
- **Status**: (Available, Borrowed, Reserved, Lost, etc.)

## 3. Book Borrowing & Return System
- Members can borrow books if available.
- The system should track:
    - Who borrowed the book.
    - Borrowing date & return due date.
    - Overdue books and fines (if applicable).
- Members should be able to return books, and the system should update the inventory.

## 4. Reservation System
- If a book is currently borrowed, members should be able to place a reservation/hold.
- The system should notify the member when the book is available.

## 5. Fine Management (Late Returns)
- If a book is returned after the due date, a fine should be calculated based on a predefined policy.
- Librarians should be able to:
    - View outstanding fines for any member.
    - Mark fines as paid.

## 6. Search & Filtering
Users should be able to search books by:
- **Title, Author, ISBN, Category, Availability**
- Filter books based on status (Available, Borrowed, Reserved).

## 7. Notifications & Alerts
Notify users via email/SMS for:
- Book due date reminders.
- Book return confirmations.
- Reservation availability.
- Fines and penalties.

## 8. Reporting & Analytics (For Librarians)
Generate reports on:
- Books borrowed/returned within a period.
- Most borrowed books.
- List of overdue books & members with outstanding fines.

## 9. Authentication & Authorization
- Secure login with **Spring Security**.
- **OAuth2 or JWT-based authentication** for APIs.
- **Role-based access control (RBAC)** for managing permissions.

## 10. Audit Logs & Activity Tracking
Maintain logs of:
- Books added, updated, removed.
- User transactions (borrowing, returning, fine payments).
- System login and logout activities.  
