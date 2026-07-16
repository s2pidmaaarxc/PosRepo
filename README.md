# SariPOS — Sari-Sari Store Point of Sale System

> **DCIT 55A — Advanced Database Management System**
> Final Examination | 2nd Semester A.Y. 2025–2026
> Cavite State University — CvSU CCAT Campus, Rosario, Cavite
> Department of Computer Studies

---

## Project Overview

**SariPOS** is a database-driven Point of Sale (POS) system designed for sari-sari store operations. It demonstrates proper database design, data preparation, and SQL-based analysis as required by the final examination of DCIT 55A — Advanced Database Management System.

The system supports two user roles — **Manager** and **Cashier** — with real-time inventory tracking, automatic receipt generation, and sales analytics.

---

## Objectives

- Design and develop a fully functional database-driven system based on a real-world scenario
- Apply proper database design with normalized tables and relationships
- Demonstrate data quality assessment, data cleaning, and SQL-based data analysis
- Generate meaningful reports and insights from a structured dataset

---

## Expected Outcomes

- A fully functional database system with properly designed tables and relationships
- A dataset containing at least 100 records with identified and resolved data quality issues
- Cleaned and transformed data using SQL operations
- Executed SQL queries for filtering, joining, and data analysis
- Generated meaningful reports and insights from the dataset
- A system demonstration showing understanding of database structure and SQL operations
- Application of real-world database management and data handling practices

---

## Database Design

### Entity-Relationship Overview

The system uses **6 related tables** with proper Primary Key (PK) and Foreign Key (FK) relationships:

| Table | Description |
|---|---|
| `users` | Stores manager and cashier accounts |
| `categories` | Product category classifications |
| `products` | Store inventory with pricing and stock |
| `orders` | Transaction records per cashier |
| `order_items` | Line items per order (many-to-many bridge) |
| `receipts` | Generated receipt records linked to orders |

### Relationships

- `users` → `orders` (1-to-many): One cashier can process many orders
- `categories` → `products` (1-to-many): One category contains many products
- `orders` → `order_items` (1-to-many): One order has many line items
- `products` → `order_items` (1-to-many): One product appears in many order items
- `orders` → `receipts` (1-to-1): One order generates one receipt

---

## System Features

### Manager Panel
- **Dashboard** — Store-wide sales overview, cashier performance charts, low stock alerts
- **Products** — Add, edit, delete products and categories; inventory status monitoring
- **Users** — Add, edit, delete cashier/manager accounts; reset passwords
- **Reports** — Date-filtered analytics: daily sales, best sellers, cashier performance, category revenue

### Cashier Panel
- **Dashboard** — Personal sales summary, hourly breakdown, top products sold
- **Point of Sale** — Product search, category filtering, cart management, checkout workflow with payment confirmation
- **Transactions** — Full transaction history with receipt viewing and order cancellation

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, JavaScript (Vanilla) |
| Backend | PHP 8.x |
| Database | MySQL 8.x |
| Charts | Chart.js 4.4.1 |
| Fonts | Plus Jakarta Sans, DM Mono |
| Server | Apache (XAMPP / WAMP) |

---

## Installation & Setup

### Prerequisites
- XAMPP / WAMP / LAMP with PHP 8+ and MySQL 8+
- Web browser (Chrome, Firefox, Edge)

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/saripos.git
   ```

2. **Move to your server's web root**
   ```bash
   # XAMPP (Windows)
   mv saripos C:/xampp/htdocs/pos_system

   # XAMPP (Linux/Mac)
   mv saripos /opt/lampp/htdocs/pos_system
   ```

3. **Configure database credentials** in `config.php`
   ```php
   define('DB_HOST',  'localhost');
   define('DB_USER',  'root');       // your MySQL username
   define('DB_PASS',  '');           // your MySQL password
   define('BASE_URL', 'http://localhost/pos_system');
   ```

4. **Start Apache and MySQL**, then open:
   ```
   http://localhost/pos_system/
   ```

5. **The database auto-initializes** on first visit — tables are created and seeded automatically. No manual SQL import needed.

### Default Login Credentials

| Username | Password | Role |
|---|---|---|
| `Admin` | `123456` | Manager |
| `Pedro_mgr` | `123456` | Manager |
| `Juan` | `123456` | Cashier |
| `Maria` | `123456` | Cashier |
| `Jose` | `123456` | Cashier |
| `Ana` | `123456` | Cashier |

---

## Project Structure

```
pos_system/
├── index.html                  # Login page
├── config.php                  # DB config, session helpers, auto-init
├── assets/
│   ├── css/
│   │   ├── style.css           # Global styles
│   │   ├── login.css
│   │   ├── pos.css
│   │   ├── mDashboard.css
│   │   ├── cDashboard.css
│   │   ├── products.css
│   │   ├── users.css
│   │   ├── transactions.css
│   │   ├── report.css
│   │   └── receipt.css
│   └── js/
│       ├── main.js             # Global JS (modals, toast, clock)
│       ├── login.js
│       ├── pos.js
│       ├── mDashboard.js
│       ├── cDashboard.js
│       ├── products.js
│       ├── users.js
│       ├── transactions.js
│       └── reports.js
├── auth/
│   ├── login.php
│   └── logout.php
├── includes/
│   ├── sidebar_manager.php
│   └── sidebar_cashier.php
├── manager/
│   ├── dashboard.php
│   ├── products.php
│   ├── users.php
│   └── reports.php
└── cashier/
    ├── dashboard.php
    ├── pos.php
    ├── transactions.php
    └── receipt.php
```

---

## Key Insights from Data Analysis

1. **Top-selling category** is Noodles and Beverages — fast-moving, low-margin items
2. **Peak transaction hours** can be tracked via the hourly sales chart on the cashier dashboard
3. **Cashier performance** varies significantly — reports allow managers to identify high and low performers
4. **Low stock alerts** are triggered at below 10 units to prevent stockouts
5. **Cancellation rate** tracking helps identify checkout friction or cashier errors

---

## System Demonstration

The demonstration covers:

1. **System Overview** — Purpose, real-world use case (sari-sari store POS)
2. **Database Explanation** — Tables, relationships, PK/FK walkthrough
3. **Data Quality Explanation** — Problems found, why they matter, how resolved
4. **SQL Demonstration** — Live SELECT, JOIN, filtering, and analytical queries
5. **Insights** — What the data reveals about store performance

---
## License

This project was developed as an academic requirement for **DCIT 55A — Advanced Database Management System** at Cavite State University CvSU CCAT Campus. For educational purposes only.

---

*SariPOS © 2025 — CvSU CCAT Campus, Department of Computer Studies*
