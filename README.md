# School-Management-System
School management system| C#,SQL (Database project)

### School Management System using C# and SQL (Database Project)

#### Overview:
The School Management System is a project designed to manage various aspects of a school's operations, focusing on adding and managing teacher and student information. The system uses C# for the front-end application development and SQL for the backend database management.

#### Key Features:

1. **Student Management**:
    - **Add Student**: Register new students with details such as name, date of birth, address, contact information, and parent/guardian details.
    - **View Student Profiles**: Maintain detailed student profiles, including academic records, attendance history, and disciplinary records.
    - **Update/Delete Student Information**: Edit or remove student information as needed.

2. **Teacher Management**:
    - **Add Teacher**: Register new teachers with details such as name, date of birth, address, contact information, qualifications, and subjects taught.
    - **View Teacher Profiles**: Maintain detailed profiles for teachers, including personal details, contact information, qualifications, and subjects taught.
    - **Update/Delete Teacher Information**: Edit or remove teacher information as needed.

#### Technical Details:

1. **Front-End (C#)**:
    - The front-end application is developed using C# with Windows Forms or WPF (Windows Presentation Foundation).
    - It provides an intuitive and user-friendly interface for managing student and teacher information.
    - It includes forms for data entry, viewing records, updating records, and deleting records.

2. **Back-End (SQL Database)**:
    - The back-end database is developed using SQL Server.
    - The database schema includes tables for students and teachers.
    - Stored procedures are used to handle complex database operations and maintain data integrity.

#### Database Schema (Example Tables):

1. **Students**:
    - StudentID (Primary Key)
    - FirstName
    - LastName
    - DateOfBirth
    - Address
    - ContactNumber
    - ParentGuardianDetails

2. **Teachers**:
    - TeacherID (Primary Key)
    - FirstName
    - LastName
    - DateOfBirth
    - Address
    - ContactNumber
    - Qualifications
    - SubjectsTaught

#### Implementation Steps:

1. **Requirement Analysis**:
    - Gather detailed requirements from stakeholders (e.g., school administrators).

2. **System Design**:
    - Design the overall architecture of the system, including the front-end application and back-end database schema.
    - Create detailed design documents, including ER diagrams for the database and UI mockups for the application.

3. **Development**:
    - Set up the development environment, including C# IDE (e.g., Visual Studio) and SQL Server.
    - Develop the front-end application using C# Windows Forms or WPF.
    - Create the database schema and implement stored procedures, triggers, and other database components.

4. **Testing**:
    - Perform unit testing to ensure each module functions correctly.
    - Conduct integration testing to ensure different modules work together seamlessly.
    - Perform user acceptance testing (UAT) with actual users to gather feedback and make necessary adjustments.

5. **Deployment**:
    - Deploy the application and database on the school’s server.
    - Provide training to school staff on how to use the system.

6. **Maintenance**:
    - Provide ongoing support and maintenance to address any issues and implement new features as required.

#### Example Code Snippets:

1. **C# Code to Add Student**:
    ```csharp
    private void AddStudent()
    {
        string connectionString = "your_connection_string";
        using (SqlConnection conn = new SqlConnection(connectionString))
        {
            string query = "INSERT INTO Students (FirstName, LastName, DateOfBirth, Address, ContactNumber, ParentGuardianDetails) VALUES (@FirstName, @LastName, @DateOfBirth, @Address, @ContactNumber, @ParentGuardianDetails)";
            SqlCommand cmd = new SqlCommand(query, conn);
            cmd.Parameters.AddWithValue("@FirstName", txtFirstName.Text);
            cmd.Parameters.AddWithValue("@LastName", txtLastName.Text);
            cmd.Parameters.AddWithValue("@DateOfBirth", dtpDateOfBirth.Value);
            cmd.Parameters.AddWithValue("@Address", txtAddress.Text);
            cmd.Parameters.AddWithValue("@ContactNumber", txtContactNumber.Text);
            cmd.Parameters.AddWithValue("@ParentGuardianDetails", txtParentGuardianDetails.Text);

            conn.Open();
            cmd.ExecuteNonQuery();
            conn.Close();
        }
    }
    ```

2. **SQL Stored Procedure to Add Teacher**:
    ```sql
    CREATE PROCEDURE AddTeacher
        @FirstName NVARCHAR(50),
        @LastName NVARCHAR(50),
        @DateOfBirth DATE,
        @Address NVARCHAR(255),
        @ContactNumber NVARCHAR(50),
        @Qualifications NVARCHAR(255),
        @SubjectsTaught NVARCHAR(255)
    AS
    BEGIN
        INSERT INTO Teachers (FirstName, LastName, DateOfBirth, Address, ContactNumber, Qualifications, SubjectsTaught)
        VALUES (@FirstName, @LastName, @DateOfBirth, @Address, @ContactNumber, @Qualifications, @SubjectsTaught);
    END
    ```

This simplified School Management System focuses on adding and managing teacher and student information efficiently.
