# EmployWise Spring Boot Employee Management System

## Project Overview
This project implements an Employee Management System using Spring Boot. It provides RESTful APIs to perform CRUD operations on employees and includes features such as retrieving the nth level manager of an employee, pagination, sorting, sending email notifications to the level 1 manager on new employee addition, and hosting the application on a free platform.

## Setup Instructions
1. Ensure you have Java JDK and Maven installed.
2. No need to make the edit in the code and properties file.
3. I have used the MongoDB Atlas as NoSQL database and configure the connection details in `application.yml`.
4. Configure SMTP server details in `application.properties` for sending email notifications.
5. Run the application
6. Access the application at `http://localhost:8080`.

## API Documentation
### Entry Level
1. **Add Employee**
   - Method: POST
   - Endpoint: `http://localhost:8080/employees`
   - Request Body: 
     ```json
     {
       "employeeName": "Arun",
       "phoneNumber": "1234567890",
       "email": "arun@gmail.com",
       "reportsTo": "managerId",
       "profileImage": "https://example.com/profile.jpg"
     }
     ```
   - Response:
     ```json
     {
       "id": "generatedId",
       "employeeName": "Arun",
       "phoneNumber": "1234567890",
       "email": "arun@gmail.com",
       "reportsTo": "managerId",
       "profileImage": "https://example.com/profile.jpg"
     }
     ```


     Note: Use the generated ID of previous employees as the manager ID for adding new employees.

2. **Get All Employees**
   - Method: GET
   - Endpoint: `http://localhost:8080/employees`
   - Response: List of all employees.

3. **Delete Employee by ID**
   - Method: DELETE
   - Endpoint: `http://localhost:8080/employees/{employeeId}`

4. **Update Employee by ID**
   - Method: PUT
   - Endpoint: `http://localhost:8080/employees/{employeeId}`
   - Request Body: Same as Add Employee

### Intermediate
5. **Get nth Level Manager of an Employee**
   - Method: GET
   - Endpoint: `http://localhost:8080/employees/managers/{employeeId}?level={n}`

6. **Get Employees with Pagination and Sorting**
   - Method: GET
   - Endpoint: `http://localhost:8080/employees/paginate?page={page}&size={size}&sort={field}`

### Advanced
7. **Send Email to Level 1 Manager on New Employee Addition**
   - Method: Implemented automatically on new employee addition.
   - Email Content: "<EmployeeName> will now work under you. Mobile number is <PhoneNumber> and email is <EmailId>".

8. **Hosted Application**
   - The application is hosted on a free platform at [https://employee-backend-production-5af8.up.railway.app/employees](https://employee-backend-production-5af8.up.railway.app/employees).

## Additional Features
- Validations and error handling are implemented for every API route.
- Email notifications are sent to the level 1 manager when a new employee is added.
- Pagination and sorting options are available for retrieving employees.

