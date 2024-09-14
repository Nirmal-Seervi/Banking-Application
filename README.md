# Banking Application

## Project Overview

The **Banking Application** is designed to improve customer management and basic banking operations, offering features for both admins and customers. The application includes customer registration, account management, and secure transaction functionality, with role-based access for admins and customers.

## Features

### Admin Role
- **Login**: Admins can securely log in using a username and password.
- **Customer Registration**: Admins can register new customers with the following details:
  - Full Name
  - Address
  - Mobile Number
  - Email ID
  - Type of Account (Savings or Current)
  - Initial Balance (minimum of 1000)
  - Date of Birth
  - ID Proof
- **Account Number Generation**: Automatically generates an account number and a temporary password for the customer.
- **Customer Management**: Admins can add, delete, modify, and view customer details (password and balance remain hidden for security).

### Customer Role
- **Account Setup**: Customers can set a new password after receiving their account number and temporary password.
- **Login & Logout**: Customers can log in with their account number and password and securely log out.
- **Dashboard**: Displays account details and balance after login.
- **Transaction History**: Customers can view the last 10 transactions, sorted by date.
- **Deposit & Withdraw**: Customers can deposit or withdraw money, with transactions recorded in the database. Withdrawals are allowed as long as the balance is not negative.
- **Account Closure**: Customers can close their accounts without admin intervention after withdrawing all funds.

### Bonus Feature
- **Download Mini Statement**: Customers can download a PDF of their last 10 transactions by clicking "Print" in the mini statement.

## Technical Specifications

- **Backend**: Java (Servlets/JSP)
- **Database**: MySQL
- **Web Server**: Apache Tomcat 9
- **IDE**: Eclipse IDE
- **Database Tools**: MySQL Server, MySQL Workbench

## Setup Instructions

### Prerequisites
- **Java Development Kit (JDK 8 or above)**: [Download JDK](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html)
- **Apache Tomcat 9**: [Download Tomcat](https://tomcat.apache.org/download-90.cgi)
- **MySQL Server**: [Download MySQL](https://dev.mysql.com/downloads/)

### Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Nirmal-Seervi/Banking-Application.git
   ```

2. **Database Setup**:
   - Create a MySQL database:
     ```sql
     CREATE DATABASE banking_app;
     ```
   - Import the provided SQL schema from the `/db` folder:
     ```bash
     mysql -u root -p banking_app < /path/to/schema.sql
     ```

3. **Configure Database Connection**:
   - Update the database credentials in the `DBConnection.java` file:
     ```java
     private static final String URL = "jdbc:mysql://localhost:3306/banking_app";
     private static final String USER = "your_mysql_username";
     private static final String PASSWORD = "your_mysql_password";
     ```

4. **Build and Deploy**:
   - Use Maven to build the project:
     ```bash
     mvn clean install
     ```
   - Deploy the `.war` file to the Tomcat `webapps` directory:
     ```bash
     <tomcat_directory>/bin/startup.sh
     ```

5. **Access the Application**:
   - Open your browser and go to `http://localhost:8080/Banking-Application`.

## Database Schema

- **Customers**: Stores customer details such as name, address, mobile number, and account type.
- **Accounts**: Stores account details including balance and account number.
- **Transactions**: Logs all deposit and withdrawal transactions for each customer.

## Future Enhancements

- Support for additional account types and services.
- Implement multi-factor authentication for enhanced security.
- Improve the UI/UX for better customer experience.

## Contributing

We welcome contributions! Please fork this repository and submit a pull request with your changes.

## License

This project is licensed under the MIT License.
