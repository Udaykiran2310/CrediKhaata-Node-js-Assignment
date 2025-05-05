# CrediKhaata-Node-js-Assignment
# CrediKhaata - Loan Tracker for Shopkeepers

## Overview

CrediKhaata is a RESTful backend service built with Node.js and Express to help small shopkeepers digitize and manage their credit sales (loans), track repayments, and get alerts for overdue payments. The application provides user authentication, customer management, loan management, repayment tracking, and loan summaries.

## Features

1.  **User Authentication:**
    -   Shopkeeper registration/login via email and password.
    -   JWT-based session management for secure access to routes.
    -   All routes are user-scoped to ensure data privacy and security.
2.  **Customer Management:**
    -   Add/edit/delete customer profiles with fields such as name, phone, address, trust score (0–10), and credit limit.
3.  **Loan (Credit Sale) Management:**
    -   Create a credit transaction with details like customerId, item description, loan amount, issue date, due date, and frequency (bi-weekly/monthly).
    -   Optional fields for interest percentage and grace days.
    -   View all active loans with status (pending, paid, overdue).
4.  **Repayment Tracking:**
    -   Record repayments (amount + date) for specific loans.
    -   Automatically update the balance on the loan after each repayment.
    -   Track partial payments and maintain accurate loan balances.
5.  **Loan Summary & Overdue Alerts:**
    -   `/summary` route per shopkeeper to provide a summary of total loaned, total collected, overdue amount, and average repayment time.
    -   `/overdue` route to list customers with overdue loans.
    -   Automatic tagging of overdue loans based on the current date.

## Bonus Features

-   SMS/WhatsApp Reminder API integration (can be mocked) to send payment reminders to customers.
-   Generate simple PDF receipts for repayments.
-   Add a webhook endpoint for repayment notifications.

## Tech Stack

-   **Node.js + Express:** Backend runtime and framework for building the RESTful API.
-   **MongoDB (preferred) or PostgreSQL:** Database for storing customer, loan, and repayment data.
-   **JWT (JSON Web Tokens):** For user authentication and session management.
-   **Moment.js or date-fns:** For handling date and time, especially for due date logic.
-   **Mongoose (if MongoDB):** For defining clear schema relationships and interacting with MongoDB.

## Installation

1.  **Clone the repository:**

    `git clone [repository-url]`
2.  **Navigate to the project directory:**

    `cd credikhaata-backend`
3.  **Install dependencies:**

    `npm install` or `yarn install`
4.  **Configuration:**
    -   Set up the MongoDB or PostgreSQL database and configure the connection string in the `.env` file.
    -   Configure JWT secret keys and other necessary environment variables in the `.env` file.
5.  **Start the application:**

    `npm start` or `yarn start`

## API Endpoints

-   `POST /auth/register`: Register a new shopkeeper.
-   `POST /auth/login`: Login an existing shopkeeper.
-   `POST /customers`: Add a new customer.
-   `GET /customers`: Get all customers for a shopkeeper.
-   `GET /customers/:customerId`: Get a specific customer by ID.
-   `PUT /customers/:customerId`: Edit an existing customer.
-   `DELETE /customers/:customerId`: Delete a customer.
-   `POST /loans`: Create a new loan.
-   `GET /loans`: Get all loans for a shopkeeper.
-   `GET /loans/:loanId`: Get a specific loan by ID.
-   `PUT /loans/:loanId`: Update an existing loan.
-   `DELETE /loans/:loanId`: Delete a loan.
-   `POST /repayments`: Record a new repayment.
-   `GET /summary`: Get a summary of loan data for a shopkeeper.
-   `GET /overdue`: Get a list of customers with overdue loans.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. Ensure all contributions align with the project’s coding standards and include appropriate tests.
