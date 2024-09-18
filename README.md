Name: BOORLA VENU GOPAL
Company: CODTECH IT SOLUTIONS
ID: CT08DS7413
Domain: PYTHON PROGRAMMING
Duration: AUGUST to SEPTEMBER 2024

OVERVIEW OF THE PROJECT

TITLE:Student Grade Management System
![Screenshot (148)](https://github.com/user-attachments/assets/84a1557b-28f9-4424-a645-58d85edc1f1a)


1. Introduction:
The Student Grade Management System is a Python program designed to help users track and manage student grades for different subjects or assignments. It allows the user to input grades, calculate the average, and display the overall grade in various formats, such as letter grades and GPA. This tool is useful for students, teachers, or administrators to keep track of academic performance.

2. Features
1. Grade Input by Subject: The program allows users to input multiple grades for various subjects.
2. Calculate Average: It calculates the overall average of the grades entered for all subjects.
3. Letter Grade Assignment: Based on the average grade, the program determines the corresponding letter grade (A, B, C, D, F).
4. GPA Calculation: The program computes the GPA based on the average grade.
5. Display Report: It generates and displays a report that includes the student's name, grades by subject, overall average, letter grade, and GPA.

3. Program Flow

1. Student Name Input: The program first prompts the user to input the student’s name.
2. Grade Entry: The user can add grades for various subjects. For each subject, the program will prompt for the subject name and the corresponding grade. This process repeats until the user enters `'done'` to finish input.
3. Grade Management: The program stores all grades under the respective subject names.
4. Average Calculation: It calculates the student's average grade across all subjects.
5. Letter Grade & GPA Calculation: The program determines the letter grade and GPA based on the overall average.
6. Report Display: The program displays a detailed report, including:
   - Student's name
   - Grades by subject
   - Overall average
   - Letter grade
   - GPA

4. Program Code

```python
class Student:
    def __init__(self, name):
        self.name = name
        self.grades = {}

    def add_grade(self, subject, grade):
        if subject in self.grades:
            self.grades[subject].append(grade)
        else:
            self.grades[subject] = [grade]

    def calculate_average(self):
        total_grades = 0
        count = 0
        for grades in self.grades.values():
            total_grades += sum(grades)
            count += len(grades)
        return total_grades / count if count != 0 else 0

    def determine_letter_grade(self, average):
        if average >= 90:
            return 'A'
        elif average >= 80:
            return 'B'
        elif average >= 70:
            return 'C'
        elif average >= 60:
            return 'D'
        else:
            return 'F'

    def calculate_gpa(self, average):
        if average >= 90:
            return 4.0
        elif average >= 80:
            return 3.0
        elif average >= 70:
            return 2.0
        elif average >= 60:
            return 1.0
        else:
            return 0.0

    def display_report(self):
        print(f"Student Name: {self.name}")
        print("Grades by Subject:")
        for subject, grades in self.grades.items():
            print(f"  {subject}: {grades}")
        average = self.calculate_average()
        letter_grade = self.determine_letter_grade(average)
        gpa = self.calculate_gpa(average)
        print(f"Overall Average: {average:.2f}")
        print(f"Letter Grade: {letter_grade}")
        print(f"GPA: {gpa:.2f}")

# Main program
student_name = input("Enter the student's name: ")
student = Student(student_name)   

while True:
    subject = input("Enter the subject (or 'done' to finish): ")
    if subject.lower() == 'done':
        break
    try:
        grade = float(input(f"Enter the grade for {subject}: "))
        student.add_grade(subject, grade)
    except ValueError:
        print("Invalid grade. Please enter a number.")

# Display the student report
student.display_report()
```

5. Explanation of Code

1. Class `Student`: 
   - The class has attributes for the student's name and a dictionary for storing grades (`grades`), where each subject maps to a list of grades.
   - The `add_grade()` method allows adding grades to subjects.
   - The `calculate_average()` method computes the average of all grades entered for the student.
   - The `determine_letter_grade()` method assigns a letter grade (A-F) based on the average grade.
   - The `calculate_gpa()` method assigns a GPA score (0.0-4.0) based on the average grade.
   - The `display_report()` method outputs the student’s name, grades by subject, overall average, letter grade, and GPA.

2. Main Program Logic:
   - The program first asks for the student’s name.
   - Then, it enters a loop where the user can input subjects and grades. This loop continues until the user types `'done'`.
   - After finishing input, the program calls the `display_report()` method to print the student's grade report.

6. Testing and Validation
Here are some example inputs and outputs for testing:

Input Example:
```
Enter the student's name: John Doe
Enter the subject (or 'done' to finish): Math
Enter the grade for Math: 85
Enter the subject (or 'done' to finish): Science
Enter the grade for Science: 92
Enter the subject (or 'done' to finish): History
Enter the grade for History: 78
Enter the subject (or 'done' to finish): done
```

 Output Example:
```
Student Name: John Doe
Grades by Subject:
  Math: [85.0]
  Science: [92.0]
  History: [78.0]
Overall Average: 85.00
Letter Grade: B
GPA: 3.00
```

7. Conclusion

This project provides an effective way to track and manage student grades, offering insights into their performance through average calculations, letter grades, and GPA. The program can be extended in various ways, such as handling weighted grades or supporting multiple students.

