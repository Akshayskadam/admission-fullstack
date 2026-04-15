
---

#  Admission Management System (Fullstack)

##  Project Overview

This is a **Fullstack Admission Management System** built using:

* **Frontend:** Angular
* **Backend:** Node.js + Express
* **Database:** MongoDB
* **File Storage:** CSV

The system allows student registration, admin login, viewing records, and deleting students.

---

##  Features

###  Student Features

* Register student details
* Data stored in:

  * MongoDB (for database operations)
  * CSV file (for backup/logging)

---

###  Admin Features

* Admin login (username/password based)
* Redirect to admin dashboard after login
* View student records from CSV
* Delete student by email

---

##  Technologies Used

### Frontend

* Angular (Standalone Components)
* TypeScript
* FormsModule & Routing

###  Backend

* Node.js
* Express.js
* MongoDB with Mongoose
* File System (fs module)
* CSV handling (`csv-parser`)

---

##  Project Structure

```
fullstack/
│── admission-form/
    │── backend/
    │   │── config/
    │   │── controllers/
    │   │── models/
    │   │── routes/
    │   │── server.js
    │   │── student.csv
    │
    │── frontend/
        │── admission-frontend/
            │── src/
            │── angular.json
            │── package.json
```
<img width="1615" height="579" alt="image" src="https://github.com/user-attachments/assets/3687957c-4a86-4dd4-ab1e-e1ecadc7bf2d" />

---

##  Backend Functionality

###  1. Register Student

* Saves data in MongoDB
* Also writes to `student.csv`

```js
POST /api/students/register
```

---

###  2. Get Students from CSV

* Reads student data using `csv-parser`

```js
GET /api/students
```

---

###  3. Delete Student

* Deletes from MongoDB
* Updates CSV file

```js
DELETE /api/students/:email
```

---

##  Frontend Functionality

###  Admin Login

* Static login credentials:

```
Username: admin
Password: admin123
```

* On success:

```ts
this.router.navigate(['/adminpage']);
```

---

##  How to Run the Project

###  1. Run Backend

```bash
cd backend
npm install
node server.js
```

---

###  2. Run Frontend

```bash
cd frontend/admission-frontend
npm install
ng serve
```

---

###  Access Application

```
http://localhost:4200
```

---

##  Data Storage

###  MongoDB

* Stores structured student data
* Prevents duplicate emails

###  CSV File (`student.csv`)

* Acts as backup
* Stores all student entries
* Updated on delete operation

---

##  Limitations

* Admin login is hardcoded (not secure)
* No authentication system (JWT/session)
* No input validation on frontend/backend
* CSV may break if data contains commas

---

##  Future Improvements

* Add JWT Authentication
* Role-based login system
* Replace CSV with full database system
* Add UI dashboard with charts
* Deploy on cloud (Render / Vercel / AWS)

---

##  Author

Akshay S Kadam

---

##  Notes

This project demonstrates:

* Fullstack development
* REST API integration
* File handling with CSV
* Angular + Node.js communication

---

---
