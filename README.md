# Test-ERD
Sample Question for ERD Design
### Problem Statement:

A **university** needs a system to manage its **students**, **courses**, and **instructors**. The system should keep track of the following:

1. **Students** must be able to enroll in **multiple courses**, and each **course** can have multiple **students**. For each course a student enrolls in, the **date of enrollment** should be tracked.
   
2. Each **course** is taught by **one instructor**, but an **instructor** can teach multiple courses. 

3. A **course** can exist without any **students enrolled**, but it must have an **instructor** assigned to it.

### Entities:
- **Student**:
  - Attributes: `student_id (PK)`, `student_name`, `email`, `date_of_birth`
  
- **Instructor**:
  - Attributes: `instructor_id (PK)`, `instructor_name`, `email`, `department`

- **Course**:
  - Attributes: `course_id (PK)`, `course_title`, `course_description`, `credits`

### Relationships:
- **One-to-Many**: Each **instructor** can teach multiple **courses**, but each **course** must have only one **instructor** (mandatory).
- **Many-to-Many**: **Students** can enroll in multiple **courses**, and each **course** can have multiple **students**. A **bridge table** will be needed to manage this relationship, with an additional attribute to capture the **date of enrollment**.

### Design the ERD:

1. **Entities**:
   - **Student**
   - **Instructor**
   - **Course**

2. **Bridge Table** for the many-to-many relationship between **Student** and **Course**:
   - **Student_Course_Enrollment**
     - Attributes: `student_id (FK)`, `course_id (FK)`, `date_of_enrollment`

### Cardinality:
- **Instructor-to-Course**: One-to-Many (each course must have one instructor, but each instructor can teach multiple courses).
- **Student-to-Course**: Many-to-Many (a student can enroll in multiple courses, and each course can have multiple students). Managed by a bridge table `Student_Course_Enrollment`.

---
