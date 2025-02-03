# Online-Quiz-Application


## 📌 Project Description
The **Online Quiz Application** is a Java-based project that allows users to take quizzes, track their scores, and provides an admin panel to manage quiz questions. The system includes authentication for both **regular users** and **administrators**. The application is built using **JDBC for database integration with MySQL** and features a simple UI using **JOptionPane**.

## 🚀 Features
- **User Authentication**: Login & Registration system for users and admins.
- **Quiz Management**: Admins can **add, edit, and delete** quiz questions.
- **Quiz Taking**: Users can attempt quizzes and get scores.
- **Score Tracking**: Users can view their past quiz results.
- **Database Integration**: Uses **MySQL** for storing users, questions, and scores.
- **Admin Control**: Only admins can manage quizzes.

## 🛠️ Technologies Used
- **Java** (Core Logic & UI)
- **JDBC** (Database Connectivity)
- **MySQL** (Database Management)
- **JOptionPane** (User Interface)
- **IntelliJ / Eclipse / VS Code** (Recommended IDEs)

## 🔧 Setup Instructions
1️⃣ **Install MySQL** and create a database named `quiz_db`.
2️⃣ **Run the SQL script** to create `users`, `questions`, and `scores` tables.
3️⃣ **Update Database Credentials** in `connectDatabase()` method.
4️⃣ **Compile and Run** the application in **IntelliJ, Eclipse, or CLI**.

## 📝 Database Schema
### **Users Table**
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL
);
```
### **Questions Table**
```sql
CREATE TABLE questions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    question_text TEXT NOT NULL,
    option1 VARCHAR(255) NOT NULL,
    option2 VARCHAR(255) NOT NULL,
    option3 VARCHAR(255) NOT NULL,
    option4 VARCHAR(255) NOT NULL,
    correct_option INT NOT NULL
);
```
### **Scores Table**
```sql
CREATE TABLE scores (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    score INT NOT NULL,
    quiz_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (username) REFERENCES users(username) ON DELETE CASCADE
);
```

## 🔑 Admin Login Credentials
- **Username:** `admin`
- **Password:** `admin123`

## 📌 Assumptions & Limitations
- Admin credentials are **hardcoded**.
- Passwords are **not encrypted**.
- Users can **only take quizzes** but cannot modify questions.
- Questions are **randomly selected** from the database.

## 📂 Folder Structure
```
Online-Quiz-App/
│-- src/
│   │-- QuizApp.java (Main application logic)
│-- database/
│   │-- quiz_db.sql (Database script)
│-- README.md (Project documentation)
│-- .gitignore (Git ignore file)
│-- LICENSE (License information)
```

## 💡 Future Enhancements
- Implement **password encryption** for security.
- Add a **timer** for each question.
- Provide a **leaderboard** feature for top scorers.
- Improve the **UI with JavaFX** for a better user experience.

## 📌 Author
This project was developed as part of a **Java development internship**. Contributions and feedback are welcome!

---
🎯 **Start your quiz journey today!** 🚀

