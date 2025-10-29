# Academic-Manangement-System
Academic Management site using html css js nodejs and mongodb
Academic Management System (AMS) Backend API
The Academic Management System (AMS) API is a robust, multi-role backend solution designed to centralize and manage core institutional data, including user authentication, course enrollment, grade tracking, scheduling, and administrative reporting. Built on the Node.js platform, this API provides secure, high-performance endpoints for integration with web and mobile frontend applications.


🌟 Features
•	Multi-Role Authentication: Secure login for Students, Teachers, and Administrators with role-based access control (RBAC).
•	Course Management: Full CRUD operations on courses, including automatic handling of enrollment caps and student waitlists.
•	Academic Records: Dedicated modules for logging and summarizing student attendance and entering/analyzing exam marks (including class averages).
•	Timetabling: Personalized timetable generation for students (based on enrollment) and teachers (based on courses taught).
•	Administrative Oversight: Centralized endpoints for managing student fees, support tickets, and system-wide announcements.
•	Scalable Architecture: RESTful design implemented with Node.js/Express and a flexible MongoDB schema.


🛠️ Technology Stack
Category	Technology	Version / Tool
Backend Runtime	Node.js	$16.x$ or higher
Web Framework	Express.js	Latest stable
Database	MongoDB	Any version ($4.x$ or $5.x$)
ODM	Mongoose	Latest stable
Security/Utilities	dotenv, path	

🚀 Getting Started
Follow these steps to set up and run the AMS API locally.
1. Prerequisites
Ensure you have the following software installed:
•	Node.js and npm (Node Package Manager)
•	A running MongoDB instance (local or hosted, typically on port 27017).

2. Installation
1.	Clone the Repository:
Bash
git clone [YOUR-REPO-URL]
cd academic-management-system-api
2.	Install Dependencies:
Bash
npm install express mongoose path dotenv
3. Configuration
1.	Create a file named .env in the root directory.
2.	Add the following configuration variables to the .env file:
Code snippet
4. Run the Server
Start the application using Node:
Bash
node server.js
You should see output indicating successful connection and server status:
✅ MongoDB connected successfully.
--- Initializing Sample Data ---
...
Sample data created successfully.
🚀 Server running on http://localhost:3000
Frontend served from index.html
Test Credentials: student1/pass, amita/pass, sachin/pass, mehak/pass
🔐 API Endpoints and Testing

The API uses Role-Based Access Control (RBAC). When testing protected routes (indicated below), you must send two mandatory headers:
1.	Content-Type: application/json
2.	x-user-role: [role] (e.g., student, teacher, or admin)
3.	x-user-username: [username] (e.g., amita or student1)
Core Authentication

Method	Endpoint	Description	Access
POST	/api/auth/signup	Register a new user (requires secretKey for teachers).	All
POST	/api/auth/login	Authenticate a user and receive role details.	All
Academic Data & Analytics
Method	Endpoint	Description	Access
GET	/api/courses/all	List all courses with teacher and enrollment details.	All
GET	/api/courses/my-courses	Get all courses taught by the authenticated teacher.	Teacher/Admin
GET	/api/timetable/:role/:username	Fetch the personalized class schedule.	All
GET	/api/analytics/marks/:studentId	Get student marks and compare them to class averages.	Student/Teacher/Admin
POST	/api/marks/entry	Log or update a student's exam score.	Teacher/Admin
GET	/api/attendance/summary/:studentId	Calculate attendance percentage per course.	Student/Teacher/Admin
Management (Teacher/Admin Access Only)
Method	Endpoint	Description	Access
GET	/api/management/fees	Get comprehensive fee status for all students (uses aggregation).	Teacher/Admin
PUT	/api/management/fees/:id	Update a student's fee payment status.	Teacher/Admin
POST	/api/management/enrollment/:courseCode	Manually enroll, waitlist, or drop a student from a course.	Teacher/Admin

🤝 Contributing
Contributions are welcome! If you find a bug or have an enhancement idea, please follow the standard GitHub workflow:
1.	Fork the repository.
2.	Create a new feature branch (git checkout -b feature/AmazingFeature).
3.	Commit your changes (git commit -m 'Add AmazingFeature').
4.	Push to the branch (git push origin feature/AmazingFeature).
5.	Open a Pull Request.
