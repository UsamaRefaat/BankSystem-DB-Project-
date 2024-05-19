# Bank System Database and Application Overview

The Bank System database is designed to support a desktop application built using C# and Windows Forms. The application provides functionalities for different user roles: Customer, Employee, and Admin. Each role has specific forms and capabilities within the system, such as account management, loan processing, and branch administration. This report details the database structure, the functionality of the desktop application, and the key interactions between different components.

## Database Schema

### Bank Table
*Stores information about different banks.*

**Fields:**  
- `Name`
- `Code`
- `BuildingNumber`
- `Street`
- `City`
- `Country`

### Branch Table
*Contains details about various branches of the banks.*

**Fields:**  
- `Number`
- `BankCode`
- `BuildingNumber`
- `Street`
- `City`
- `Country`

### Customer Table
*Stores customer information.*

**Fields:**  
- `SSN`
- `FirstName`
- `MiddleName`
- `LastName`
- `BuildingNumber`
- `Street`
- `City`
- `Country`
- `Password`

### Employee Table
*Contains employee information and admin status.*

**Fields:**  
- `SSN`
- `FirstName`
- `MiddleName`
- `LastName`
- `BuildingNumber`
- `Street`
- `City`
- `Country`
- `Password`
- `Admin`

### Account Table
*Contains account details for customers.*

**Fields:**  
- `Number`
- `BranchNumber`
- `BankCode`
- `Type`
- `Balance`
- `CSSN`

### Loan Table
*Stores loan details associated with specific branches and banks.*

**Fields:**  
- `Number`
- `Type`
- `BranchNumber`
- `BankCode`

## Desktop Application Forms and Functionality

1. **User Role Selection Form**
    - Allows users to choose their role: Customer, Employee, or Admin.
    - Redirects to the appropriate login form based on the selection.

2. **Login Form**
    - Authenticates users based on their role and credentials.
    - Admins and Employees can access additional functionalities compared to Customers.

3. **Sign Up Form**
    - Enables new users to register as Customers.
    - Captures necessary details and stores them in the Customer table.

4. **Loan Request Form (by Customer)**
    - Enables customers to request loans.
    - Allows customers to choose from their multiple accounts (if they exist).
    - Captures necessary loan details to send the request.
    - Updates the customer account live.

5. **Loan Logs Form**
    - Displays all loan requests and their statuses.
    - Shows customer details, account details, and loan details.

6. **New Branch Form (by Admin)**
    - Admins can create new branches for existing banks.
    - Captures branch details and updates the Branch table.

7. **New Loan Form (by Admin)**
    - Admins can define new loan types available at branches.
    - Updates the Loan table with new loan information.

8. **Report Form**
    - Displays statistical reports about recent loan requests.
