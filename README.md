# Old Age Home Medication Management System

A simple, user-friendly medication management website built for caretakers in an old age home. The application is designed to help staff manage residents, medication schedules, stock levels, reminders, and daily medication reports.

## Features
- Secure login for administrators and caretakers
- Resident management with add, edit, view, and archive support
- Medical history record tracking
- Medicine and dosage management
- Medication reminders and daily dose tracking
- Stock management with expiry and low-stock alerts
- Dashboard overview with key statistics
- Daily medication and stock reporting
- Responsive design for desktop, tablet, and mobile
- Form validation and confirmation messaging

## Tech Stack
- Frontend: HTML, CSS (internal), JavaScript
- Backend: Python Flask
- Database: MySQL

## Project Structure
```text
Medication_System/
├── app.py
├── requirements.txt
├── schema.sql
├── sample_data.sql
├── .gitignore
├── README.md
└── templates/
    └── index.html
```

## Prerequisites
- Python 3.10+
- MySQL 8.0+
- Pip package manager

## Installation
1. Clone the project repository.
2. Open a terminal in the project folder.
3. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
```
4. Install dependencies:
```bash
pip install -r requirements.txt
```
5. Create the MySQL database:
```sql
CREATE DATABASE medication_system;
CREATE USER 'medadmin'@'localhost' IDENTIFIED BY 'MedPass123';
GRANT ALL PRIVILEGES ON medication_system.* TO 'medadmin'@'localhost';
FLUSH PRIVILEGES;
```
6. Update your environment variables if needed:
```bash
export DB_HOST=localhost
export DB_USER=medadmin
export DB_PASSWORD=MedPass123
export DB_NAME=medication_system
export SECRET_KEY=your-secret-key
```
7. Run the database schema script:
```bash
mysql -u medadmin -p medication_system < schema.sql
```
8. Load sample data:
```bash
mysql -u medadmin -p medication_system < sample_data.sql
```
9. Start the app:
```bash
python app.py
```
10. Open the browser at:
```text
http://localhost:5000
```

## Default login credentials
- Administrator: `admin` / `admin123`
- Caretaker: `caretaker` / `caretaker123`

The application automatically creates and hashes these default accounts on first startup if they do not already exist.

## Database Schema
The project includes `schema.sql` with the following tables:
- `users`
- `residents`
- `medical_history`
- `medicines`
- `medication_schedule`
- `medication_log`
- `stock_alerts`

## Sample Data
The `sample_data.sql` file includes example residents, medicines, stock levels, and reminder records so the dashboard can display realistic values immediately.

## Notes
- The app is built with an internal CSS style tag to match the requirement for internal CSS.
- The interface is designed for simple operation with readable text, large controls, and clear alerts.
- The dashboard is responsive and suitable for tablet and mobile devices.

## Security
- Passwords are stored using Werkzeug password hashing.
- Only authenticated users can access dashboard features.

## License
This project is for educational and demonstration purposes.
