# Flight Reservation System

This is a clean, modern web app built to handle flight scheduling, passenger sign-ups, and seat bookings. It mimics how real database management systems handle information using structured, efficient code logic.

---

## How Data is Managed (Data Structures)

To make sure the app runs quickly and saves data correctly, it uses specific ways to organize information behind the scenes:

### 1. Passenger Records (Binary Search Tree - BST)
Passenger accounts are stored and managed using a **Binary Search Tree (BST)** logic, sorted alphabetically by their unique Passenger ID.
* **Why it matters**: It makes searching for a specific passenger incredibly fast. Instead of looking through every single account, it cuts the search time down significantly using a $O(\log n)$ lookup strategy.
* **Printing Data**: When the admin wants to see all passengers, the system walks through the tree "in-order" so the final list shows up perfectly sorted from A to Z.

### 2. Flights & Bookings (Singly Linked Lists)
Available flights and user reservations are structured like nodes in a **Singly Linked List**.
* **Head Insertion**: When an admin adds a new flight, it is instantly pushed to the very front of the list. This takes almost no processing power ($O(1)$ complexity) and makes sure new data shows up first.
* **Searching**: When a passenger wants to buy a seat, the system loops through the list step-by-step to find the matching Flight ID, updates the seat count, and saves the change.

### 3. Fake File System (Local Storage Persistence)
In a desktop C++ project, you usually read and write data to `.txt` files. Since this runs in a web browser, we simulate that using **Web Local Storage**:
* Every time a flight is added, a seat is booked, or an account is made, the app converts the data into a text string (JSON) and saves it directly inside your browser.
* When you refresh the page, the app reads that text string back, instantly restoring your data so nothing is lost!

---

## Main Features

### Admin Portal
* **Add Flights**: Create new flights by filling out simple forms. The system automatically checks for typos or invalid formatting before saving.
* **System View**: Look at global logs to see every single flight scheduled, every seat booked, and every registered passenger in the system.

### Passenger Portal
* **Create Account & Login**: Passwords and user profiles are securely checked against our storage tree before letting anyone log in.
* **Book Seats**: Pick a flight, type in how many seats you want, and the system handles the total price math and subtracts the available seats automatically.
* **Cancel Bookings**: Changed your mind? You can cancel your entire ticket to get your seats back, or do a partial cancellation (e.g., cancel 1 seat out of 3) which updates your price automatically.

---
# Data Formats Allowed (Validation)

The system uses strict pattern checkers (**Regex Validation**) to ensure users enter correct data formats.  
If the input does not match the required pattern, the system blocks the action and displays a warning toast notification.

| Form Field | What it Accepts | Example |
|------------|----------------|---------|
| Flight ID | Letters and numbers only, max 10 characters | `PK501`, `AA99` |
| Departure / Arrival | Letters only (no numbers or spaces) | `Lahore`, `Karachi` |
| Departure Time | `YYYY-MM-DD HH:MM AM/PM` format | `2026-06-15 08:30 AM` |
| Email Address | Standard email format | `ali@example.com` |
| Phone Number | Exactly 11 digits | `03001234567` |
| Passport Number | Letters and numbers, between 6–9 characters | `AB123456` |
| Password | Exactly 8 numeric digits | `12345678` |

---
## How to Run the Project

Since this project runs entirely inside the browser without needing complex backend servers, setting it up is incredibly easy:

1. **Download the code** onto your computer.
2. **Double-click the `index.html` file** to open it instantly in Google Chrome, Microsoft Edge, or Safari.
3. *Alternative (Recommended)*: If you use VS Code, right-click `index.html` and click **Open with Live Server** for a seamless experience.

## 🌐 Live Demo

You can also try out the application directly in your browser without downloading any files!

* **Click here to view the live project:** [View Live Demo](https://ariba-1.github.io/Flight_reservation_system/)

---

## Test Login Credentials

To save you from creating an account from scratch during your evaluation, you can jump straight into the Admin Dashboard using these default credentials:

* **Admin Username:** `user`
* **Admin Password:** `123`
