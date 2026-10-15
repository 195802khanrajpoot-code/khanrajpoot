# Khan Academy

School and college management app. C++17, Qt 6 (Widgets + Sql), MySQL.

## Setup

1. Install Qt 6 (with the Sql module and the MySQL driver `QMYSQL`), CMake, and MySQL.
2. Create the database:

       mysql -u root -p < schema.sql

3. Build:

       cmake -B build
       cmake --build build

4. Run (set your MySQL details if they differ from the defaults):

       KA_DB_HOST=127.0.0.1 KA_DB_PORT=3306 KA_DB_NAME=khan_academy \
       KA_DB_USER=root KA_DB_PASS=yourpassword ./build/KhanAcademy

Default login: `admin` / `admin123` (change it after first login).

## Structure

- `main.cpp` - starts the app: connect to DB, show login, open main window
- `database.*` - MySQL connection and login check
- `loginwindow.*` - login dialog
- `mainwindow.*` - main window "Khan Academy" with a role-based sidebar
- `schema.sql` - database and users table

## Roles

- admin: all modules
- teacher: Dashboard, Students, Attendance, Exams
- accountant: Dashboard, Fees

## Next

Students module (tables + screen), then Teachers, Attendance, Fees, Exams.
