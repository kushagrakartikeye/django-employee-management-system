Employee Management System (EMS)
A robust Django-based Employee Management System for modern HR workflows. Easily manage employees, departments, attendance, and performance, now with RESTful APIs, authentication, analytics, and a ready-to-deploy Docker setup.

📦 Features
Employee Directory: Track and manage employees with department assignments.

Department Management: Organize employees into customizable departments.

Attendance Tracking: Log employee attendance daily.

Performance Reviews: Record and rate employee performance periodically.

User Authentication: Secure admin-only and API access with DRF authentication.

REST APIs: Fully-documented CRUD, filtering, and search endpoints—ready for frontend or 3rd-party integration.

API Documentation: Interactive Swagger UI for discoverable development.

Database Seeding: Instantly generate realistic demo data.

Analytics Dashboards: (Optional) Visualize employee stats with Chart.js.

Containerized Deployment: Effortless cloud or local run with Docker & Compose.

Environment-based Config: Manage settings securely via .env.

Extensive Setup & Usage Documentation: Start in minutes!

Bonus: Ready for PostgreSQL, perfect for production use.

🚀 Quick Start
1. Clone the Repository
bash
git clone https://github.com/wojtek9502/django-employee-management-system.git
cd django-employee-management-system
2. Environment & Configuration
Copy .env.example to .env and fill in your secrets, PostgreSQL URL, etc.

bash
cp .env.example .env
Example .env variables:

text
DEBUG=True
SECRET_KEY=your_secret
DATABASE_URL=postgres://user:password@localhost:5432/emsdb
3. Install Dependencies
bash
pip install -r requirements.txt
4. Apply Migrations
bash
python manage.py migrate
5. Seed the Database (Fake Data)
Automatically generate departments, employees, attendance, and performance reports:

bash
python manage.py seed_data
6. Create Admin/Superuser
bash
python manage.py createsuperuser
7. Run the Server
bash
python manage.py runserver
Go to http://127.0.0.1:8000/

8. API Documentation (Swagger)
Access all RESTful endpoints interactively at:
http://127.0.0.1:8000/swagger/

9. Docker Deployment (Optional)
Build and run everything (app + db) with Docker Compose:

bash
docker-compose up --build
🗄 Project Structure
text
employee-management-system/
├── employees/             # Employee management (models, views, api)
│   └── management/commands/seed_data.py  # Data seeder
├── attendance/            # Attendance, performance tracking
├── employee_project/      # Project settings, main URLs
├── templates/             # (Optional) For HTML dashboards/charts
├── requirements.txt
├── Dockerfile             # Container build definition
├── docker-compose.yml     # Dev environment
├── .env.example           # Sample environment config
├── README.md
└── ...
🛠️ Tech Stack
Backend: Django 4.x, Django REST Framework

Database: PostgreSQL (with SQLite fallback)

API Docs: Swagger via drf-yasg

Fake Data Generation: Faker

Filtering: django-filter

Auth: DRF Token Auth (or JWT, as configured)

Visualization: Chart.js (optional)

Containerization: Docker, docker-compose

🧑💻 Core Endpoints & Features
/api/employees/ – CRUD Employee

/api/departments/ – CRUD Department

/api/attendance/ – Log and query attendance

/api/performance/ – Add/find performance reviews

Filtering, Pagination, Search, Sorting out of the box (see Swagger docs)

/swagger/ – Full API docs

📊 Analytics & Visualization
Employees per Department: Pie Chart

Attendance Overview (Monthly): Bar Chart

(Available at /charts/, requires enabling the visualization module.)

👮 Authentication & Security
Endpoints secured with token-based authentication.

Easy superuser/admin creation.

📝 Development & Contribution
Modular Django apps: easy to extend (HR, Payroll, Roles, etc).

High code quality, readable and PEP8-compliant.

Contributions welcome! Create issues and PRs.

🧪 Testing
Unit tests available for all critical APIs.

To run tests:

bash
python manage.py test
☁️ Deployment
Ready for deployment to Heroku, Render, Railway, or any Docker-based cloud.

For production, set DEBUG=False and define ALLOWED_HOSTS in .env.

🚧 Troubleshooting
Common async errors (e.g., Python < 3.5) and how to fix.

Ensure correct Python/PostgreSQL versions.

For Windows: Use WSL2/Docker Desktop for best compatibility.

📄 License
MIT
