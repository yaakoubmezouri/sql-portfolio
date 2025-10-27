# Honor Roll — School Database

**Objective:** List students who earned **A** in *Math Basics (101)* during *Fall Semester.*

---

## 🧱 Database Schema
**Tables:**
- Students (student_id, first_name, last_name, grade_level, birth_date)
- Enrollments (enrollment_id, student_id, course_id, semester, grade)

---

## 💻 SQL Query
```sql
SELECT s.first_name,
       s.last_name,
       e.grade,
       e.semester
FROM Students AS s
JOIN Enrollments AS e
  ON s.student_id = e.student_id
WHERE e.course_id = 101
  AND e.semester = 'Fall'
  AND e.grade = 'A'
ORDER BY s.last_name ASC;
