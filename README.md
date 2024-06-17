# File Hide System

## Overview
The File Hide System is a Java-based application that allows users to hide and unhide files on their system securely. The project is built using Maven and integrates MySQL for database management. It features user authentication, including signup and login, using email verification with OTP (One-Time Password) sent via the Java Mail API. Users can hide, view, and unhide files based on unique IDs and file paths.

## Features
- **User Authentication**: 
  - Sign up with email verification.
  - Login via OTP sent to the user's email.
  - Uses Google account app password for secure email access.
- **File Management**:
  - Hide files using a unique ID and file path.
  - View hidden files.
  - Unhide files using the unique ID.

## Technologies Used
- **Java**
- **Maven**
- **MySQL**
- **Java Mail API** (Reference: [Java Mail API 1.6.2](https://mvnrepository.com/artifact/com.sun.mail/javax.mail/1.6.2))

## Getting Started

### Prerequisites
- Java Development Kit (JDK) installed.
- Maven installed.
- MySQL server running.
- A Google account with an app-specific password for sending emails.
- IDE (preferebly IntelliJ IDE)

### Setup Instructions

1. **Clone the Repository**
   ```sh
   git clone https://github.com/yourusername/file-hide-system.git
   cd file-hide-system
   ```

2. **Configure MySQL Database**
   - Create a database named `file_hide_system`.
   - Run the following SQL script to create the `users` table:
     ```sql
     CREATE DATABASE file_hide_system;
     USE file_hide_system;
     
     CREATE TABLE users (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(100) NOT NULL,
       email VARCHAR(100) NOT NULL,
       otp VARCHAR(10),
       is_verified BOOLEAN DEFAULT FALSE
     );
     ```

3. **Configure Application Properties**
   - Update the `src/main/resources/application.properties` file with your MySQL database credentials and Google account app password for email sending:
     ```properties
     db.url=jdbc:mysql://localhost:3306/file_hide_system
     db.username=your_db_username
     db.password=your_db_password
     
     mail.smtp.host=smtp.gmail.com
     mail.smtp.port=587
     mail.smtp.username=your_email@gmail.com
     mail.smtp.password=your_app_password
     mail.smtp.auth=true
     mail.smtp.starttls.enable=true
     ```

4. **Build and Run the Application**
   ```sh
   mvn clean install
   mvn exec:java -Dexec.mainClass="com.yourpackage.Main"
   ```

## Usage

### Signup
1. Run the application.
2. Enter your name and email address.
3. An OTP will be sent to your email.
4. Enter the OTP in the application to complete the signup process.

### Login
1. Enter your registered email address.
2. An OTP will be sent to your email.
3. Enter the OTP in the application to log in.

### File Operations
- **Hide a File**: Provide the file path you want to hide.
- **View Hidden Files**: List all files that are currently hidden.
- **Unhide a File**: Provide the unique ID of the file you want to unhide.

## Screenshots
Below are some screenshots showcasing the output and process of the File Hide System:

1. Signup Process
![Screenshot 2024-06-17 181857](https://github.com/mayurmundankar/File-Hide-System/assets/100030459/d2a8eeea-1188-4c19-9f54-53551397905d)

2. Email OTP Verification
![Group 175 (2)](https://github.com/mayurmundankar/File-Hide-System/assets/100030459/c7016897-351a-4f9d-a19c-7d1a995f3ff2)
![Screenshot 2024-06-17 181948](https://github.com/mayurmundankar/File-Hide-System/assets/100030459/a5076c67-3885-4719-b3df-075bc549e3b0)

4. Hide File
![Screenshot 2024-06-17 182011](https://github.com/mayurmundankar/File-Hide-System/assets/100030459/a8a84b0f-7acc-46a1-9e81-ecae5e701f89)

5. MySQL Command Line Client
![Screenshot 2024-06-17 182133](https://github.com/mayurmundankar/File-Hide-System/assets/100030459/dfbc6938-62db-44a6-a5cd-0a883e909217)
![Screenshot 2024-06-17 182141](https://github.com/mayurmundankar/File-Hide-System/assets/100030459/6f29c58c-59d2-4d63-9af2-c6a0fdea4f80)

6. View Hidden Files
![Screenshot 2024-06-17 182654](https://github.com/mayurmundankar/File-Hide-System/assets/100030459/665e4655-f2a9-4fda-96ad-2dff4f43905f)

7. Unhide File
![Screenshot 2024-06-17 182654](https://github.com/mayurmundankar/File-Hide-System/assets/100030459/91dfcdfc-8044-443d-b4c0-8551ce4ca14c)

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request for any improvements or bug fixes.

## License
This project is licensed under the MIT License. See the (LICENSE) file for details.

## Contact
For any questions or issues, please open an issue on the GitHub repository or contact [mayurworkplace@gmail.com](mailto:mayurworkplace@gmail.com).

---

Feel free to reach out if you have any questions or need further assistance with the setup. Enjoy using the File Hide System!
