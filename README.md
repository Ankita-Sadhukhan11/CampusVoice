# CampusVoice: A Student Feedback Management System

A Java web application where students submit feedback about campus services (teaching, Wi-Fi and more). All feedback is stored in an Oracle database and shown in a records table.

Mini project for **Advanced Internet Programming (26CAH-614)**, MCA (Data Science), Semester 1, Chandigarh University.

## Features
- Feedback form with UID, Name, Email, Category, Rating and Feedback
- Feedback is saved in an Oracle database using JDBC
- "View All Feedback" page shows every record in a table

## Technologies Used
| Layer | Technology |
|---|---|
| Front end | HTML |
| Server side | Java Servlet |
| Database connectivity | JDBC (ojdbc11.jar) |
| Database | Oracle FreeSQL |
| Server | Apache Tomcat 9 |
| IDE | Eclipse |

## How It Works
1. The student fills the feedback form (index.html) and clicks Submit.
2. The Servlet reads the form data and saves it in the FEEDBACK table using JDBC.
3. "View All Feedback" makes the Servlet read all rows from the table and show them in an HTML table.

## Database Table
```sql
CREATE TABLE feedback (
    id        NUMBER GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    u_id      VARCHAR2(20)  NOT NULL,
    name      VARCHAR2(50)  NOT NULL,
    email     VARCHAR2(100) NOT NULL,
    category  VARCHAR2(30)  NOT NULL,
    rating    NUMBER        NOT NULL,
    comments  VARCHAR2(500)
);
```

## How to Run
1. Create the FEEDBACK table in Oracle FreeSQL using the SQL above.
2. Import the project into Eclipse.
3. Add ojdbc11.jar to src/main/webapp/WEB-INF/lib.
4. Update the database details in DBConnection.java.
5. Run on Apache Tomcat 9 and open http://localhost:8080/StudentFeedbackSystem/

**Feedback Form**
<img width="1920" height="1080" alt="Screenshot (431)" src="https://github.com/user-attachments/assets/13f8ca7b-659d-449c-bfa2-e1c94d5aa792" />


**Submission Result**
<img width="1920" height="1080" alt="Screenshot (441)" src="https://github.com/user-attachments/assets/89fe2590-ed10-4c3b-862c-b3aefc002b90" />


**All Feedback Records**
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3bbabc84-a844-4876-a864-f00749bb3c40" />


**Data in Oracle Database**
<img width="1920" height="1080" alt="Screenshot (442)" src="https://github.com/user-attachments/assets/c7eb9c6d-f3c0-43f5-ab8b-3f9fdf5e0721" />
