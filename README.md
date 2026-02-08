# SQL-FINALS

SQL Final Project — A simple role-based academic grading and management system.

## Project Overview

This repository contains a PHP-based web application for managing students, professors, subjects, sections, and grades. The application provides role-based access for Admin, Professor, and Student accounts and covers common academic workflows such as creating accounts, assigning subjects, viewing and setting grades, and managing sections.

The project was created as a final assignment and demonstrates CRUD operations, session-based authentication, and basic front-end styles for a small college system.

## Technologies

- **Languages:** PHP, HTML, CSS, JavaScript, SQL
- **Database:** MySQL / MariaDB (any SQL-compatible server)
- **Web server:** Apache, Nginx, or the built-in PHP development server

## Key Features

- Role-based login and session handling for Admin / Professor / Student
- Admin dashboard to add/remove Professors, Students, Subjects, and Sections
- Assign/unassign subjects to professors and sections
- Professors can set and update student grades per subject/section
- Students can view their grades and profile information
- Basic front-end styles and small client-side scripts for UX (row highlighting, small UI helpers)

## Project Structure (important files and folders)

- `sqlRevise/` — main application folder
  - `loginPage.php` — login entry page
  - `storeAndVerify.php` — login verification and session creation
  - `logOut.php` — end session
  - `adminAcc/` — admin pages and management tools
  - `profAcc/` — professor pages and grading tools
  - `studentAcc/` — student pages and grade views
  - `*.css` and `*.js` files — styles and small scripts used by pages

Examples:
- `sqlRevise/adminAcc/adminPage.php` — Admin dashboard
- `sqlRevise/profAcc/profMain.php` — Professor dashboard
- `sqlRevise/studentAcc/studentsPage.php` — Student area

Note: The repository is organized by role to make it easy to find the relevant UI and logic for each user type.

## Setup / Installation

Requirements:
- PHP 7.4+ (or PHP 8.x)
- MySQL or MariaDB
- A local web server (XAMPP, WAMP, MAMP) or production LAMP stack

Quick setup (local with XAMPP/WAMP):

1. Place the `sqlRevise` folder in your web server's document root (for XAMPP: `C:\xampp\htdocs\`, for WAMP: `C:\wamp64\www\`).
2. Create a MySQL database for the project, for example `sql_finals`.
3. Import the database schema and initial data. If a `.sql` schema file is provided (not included here), import it with phpMyAdmin or the MySQL CLI:

   - phpMyAdmin: open the database, click Import, and upload the `.sql` file.
   - Command line (Windows `cmd.exe`):

     `mysql -u <db_user> -p <db_name> < path\\to\\schema.sql`

4. Update database connection settings used by the app. Search for files that define DB connection credentials (common files to check: `sqlRevise/storeAndVerify.php`, or any `*_connect.php`/`config.php` if present) and set your DB host, username, password and database name.

5. Start your web server and open the app login in a browser, for example:

   `http://localhost/sqlRevise/loginPage.php`

6. Log in using a seeded Admin / Professor / Student account if sample users were provided. If not provided, create accounts using the Admin pages (you may need to create an initial admin record directly in the DB).

## Usage Notes (quick)

- Admin: manage users, subjects, sections, and assignments via `sqlRevise/adminAcc/` pages.
- Professor: view assigned subjects/sections and set student grades via `sqlRevise/profAcc/` pages.
- Student: log in to view grades and profile under `sqlRevise/studentAcc/`.

## Configuration hints

- If authentication fails, confirm DB credentials and table names match those expected in the PHP code.
- Session handling is file-based by default; ensure PHP sessions are writable on your system.
- File locations and include paths assume the `sqlRevise` folder is placed at server document root or reachable via your server configuration.

## Security & Improvements

- This educational project demonstrates basic functionality and is not hardened for production.
- Recommended improvements before production:
  - Use prepared statements / parameterized queries everywhere to avoid SQL injection.
  - Centralize DB credentials (`config.php`) and avoid embedding credentials across files.
  - Add CSRF protection for POST actions.
  - Use HTTPS and secure cookies for session cookies.

## Contributing

If you plan to extend the project:

- Fork the repo and add features or bug fixes.
- Keep front-end and back-end code separate where possible and add a `config.php` for DB and app-wide constants.

## Troubleshooting

- 500 Internal Server Error: check PHP error logs or enable `display_errors` in `php.ini` for development.
- Database connection errors: check host, username, password, database name, and that MySQL is running.
- Missing pages: ensure the `sqlRevise` directory is in your web root and that file permissions allow the web server to read them.

## Author / Notes

This project was created as a college final project. For questions about running or extending the app, open an issue or contact the author (if contact details are available in project metadata).

# SQL-FINALS
SQL Final Project - 93/100
May 7, 2024
