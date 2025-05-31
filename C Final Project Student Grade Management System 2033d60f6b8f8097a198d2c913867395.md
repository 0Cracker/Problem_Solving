# C Final Project: Student Grade Management System

# **Project Goal**

Build a **command-line grade management system** where instructors can manage student records and students can check their grades. The project focuses on **file I/O**, **structs**, and **basic algorithms**.

# **System Users**

- **Instructor**: Can add/edit/delete student records, calculate averages, and assign letter grades.
- **Student**: Can view their grade by entering their student ID.

All menu selections must be made using numbers.

# **1. Startup Menu**

<aside>

```cpp
=== Grade Management System ===
1. Instructor Menu
2. Student Menu
3. Exit
```

</aside>

> **1-1 Instructor Menu**
> 
- go to the Instructor menu

> **1-2 Student menu**
> 
- Please enter the student ID:
- If the student ID is found, go to the Student Menu
- If the student ID can’t be found, print error message and go back to Startup Menu.

“Cannot find {student_ID}!\n”

Ex1)

<aside>

Please enter the student ID: 2022333444

“Cannot find 2022333444!

</aside>

Ex2)

<aside>

Please enter the student ID: 2025999888

=== Student Menu ===

1. Show  my report card
2. show the overall rank, average, mid, min, max score
3. show the certain subject rank, avg, mid, min, max
4. Log Out
</aside>

> **1-3 Exit**
> 

Terminate the program. don’t print any messages

# **1. Instructor**

<aside>

```cpp
=== Instructor Menu ===

1. Add a new Student
2. Edit Student Grades
3. Delete Student Record
4. Display All Students
5. Calculate Grade Averages and Assign Letter Grades
6. Give a Feedback
7. Log Out
```

</aside>

**Student Data Format (in file)**

Each line in `grades.txt`:

```
student_id|name|grade1|score1|grade2|score2|grade3|score3 .....|average|total_grade|Student's Opinion|Instructor's feedback

```

Example:

`20210001|Alice|Math|90|English|100|Korean|80|90.00|A|I wanna get A+|Of course you can`

By default, each function should return to the Instructor menu after completion.

> **1-1 Add a new Student**
> 
- Append a new student to the end of grades.txt as a new line.
- Student ID must also be received.
- If the student ID already exists in the text file, print “The student ID already exists!\n”
- Names may be duplicated.

Ex)

<aside>

 Please input a new student’s ID: 2025999888

Please input a new student’s name: Dorothy

</aside>

<aside>

Please input a new student’s ID: 20210001

The student ID already exists!

</aside>

> **1-2 Edit Student Grades**
> 
- Ask for the student ID
- If the ID does not exist, print the error message “Cannot find the student ID!”.
- If the subject name already exists, update the score.
- If it does not exist, append it after the last grade.

Also update average and letter grade.

Ex)

<aside>

Please input the Student ID: 20210001

Please input the subject and score: Geology 88 English 80

</aside>

Before:

`20210001|Alice|Math|90|English|100|Korean|80|90.00|A|I wanna get A+|Of course you can`

After:

`20210001|Alice|Math|90|English|100|Korean|80|Geology|40|90.00|A|I wanna get A+|Of course you can`

If the grade cannot be changed due to invalid input, print “cannot change!”

Ex)

<aside>

Please input the Student ID: 20210001

Please input the subject and score: Geology English 80

Cannot change!

</aside>

> **1-3 Delete Student Record**
> 
- Receive student ID input
- Remove the corresponding row from the txt file.
- If the ID doesn’t exist, print: “The student ID does not exist!\n”

Ex)

<aside>

Please input the Student ID:  20210001

</aside>

If it succeeded, no message needs to be printed.

<aside>

Please input the Student ID:  20210002

The student ID does not exist!

</aside>

> **1-4 Display All Students**
> 
- Display all information from the txt file.

Ex)

<aside>

2021333444|Jinse|Math|10|English|10|Coding|100|It was my pleasure to be your TA. 

2022777444|Mark|English|50|Physics|100|I would be happy, if you all can get A+.

</aside>

> **1-5 Calculate Grade Averages and Assign Letter Grades**
> 
- Write the average score and final letter grade to the txt file.
- No need to print to the prompt.
- Average score must be displayed to two decimal places (round at the third digit).
- Make sure average and letter grade are placed immediately after the last grade.

Ex)

`20210001|Alice|Math|90|English|100|Korean|80|Thank you so much for the semester`

→  after insertion:

`20210001|Alice|Math|90|English|100|Korean|80|90.00|A+|Thank you so much for the semester`

A+: score≥90

A: 90>score ≥80

B+: 80> score ≥70

B: 70> score ≥60

C+: 60> score  ≥50

C: 50> score ≥40

F:  score >40

> **1-6 Give Feedback**
> 

<aside>

```cpp
===  Feedback Menu ===

1. Back to the Instructor Menu
2. Find a student by a word
3. Find a student by a phrase
4. Find a student by multiple words
5. Find a student by ID
```

</aside>

- Use the student opinions to search for matching rows.
- If feedback already exists, replace it with new feedback.
- If no matching row is found, print:
“cannot find any students!\n”

> **1-6-1. Find a student by ID**
> 
- Student ID must match exactly.
- If found, print the entire row from the txt file.

Ex) 

<aside>

 Please enter student ID: 2022333444

2022333444|Alice|Math|90|English|100|If I can get A+, I would be so Happy, Prof. Tamer. 

Please enter the feedback: I hope the end of the semester comes.

</aside>

In this case:

2022333444|Alice|Math|90|English|100|If I can get A+, I would be so Happy, Prof. Tamer. 

→

2022333444|Alice|Math|90|English|100|If I can get A+, I would be so Happy, Prof. Tamer.|I hope the end of the semester comes.

<aside>

Please enter student ID: 2022333999

cannot find any students!

</aside>

> **1-6-2. Find a student by multiple words**
> 
- Print all rows where the opinion contains *all* of the input words, regardless of order.
- Must be case-insensitive

Ex) I happy == i happy

Ex) 

2022333444|Alice|Math|90|English|100|If I can get A+, I would be so Happy, Prof. Tamer. #(o)

2022777444|Mark|English|50|Physics|100|You will be happy, if I could get A+. #(o)

2022777444|Mark|English|50|Physics|100|Be happy.  #(x)

Total Example)

<aside>

 Please enter words: I happy

2022333445|Ace|Math|90|English|100|If I can get A+, I think I would be happy, Prof. Tamer.  

2022333475|Ace|Math|90|English|100|95.00|A+|I can be happy| You did a great Job.

2025333665|Selin|Physics|50|Math|30|40.00|F|What a Happy Happy Cat! I wanna get a new cat| You need to think one more.

please enter the student ID: 2022333999

cannot find any students!

</aside>

> **1-6-3. Find a student by a phrase**
> 
- Find rows where the exact input phrase exists in the opinion.
- Case-sensitive.

 Ex) think A ≠ think a

Ex) Please enter words: think A

2022333445|Ace|Math|90|English|100|I think A.  #(o)

2022333445|Ace|Math|90|English|100|I think you are a pretty girl.  #(x)

2022333445|Elis|Math|70|English|100|I am thinking about A.  #(x)

Total Example)

<aside>

 Please enter words: be happy

2022333445|Ace|Math|90|English|100|If I can get A+, I think I would be happy, Prof. Tamer.  

2022333475|Ace|Math|90|English|100|95.00|A+|I can be happy| You did a great Job.

2025333665|Selin|Physics|50|Math|30|40.00|F|I can be happy even if I got F!| You need to think one more.

please enter the student ID: 2022333475

please enter the feedback: You should have studied harder.

</aside>

In this case:

2022333475|Ace|Math|90|English|100|95.00|A+|I can be happy| You did a great Job.

→

2022333475|Ace|Math|90|English|100|95.00|A+|I can be happy| You should have studied harder.

> **1-6-4. Find a student by a word**
> 
- Print all rows where the opinion *does **not** contain* the exact ‘word’.

Ex)

Please enter a word: late

2022333444|Alice|Math|90|English|100| I love you all guys. # (o)

2022333183|John|Geology|77|English|30| I submitted the last assignment late. # (x)

Total Example)

<aside>

Please enter a word: late

2022333444|Alice|Math|90|English|100| I love you all guys. 

2022333474|Alice|Math|90|English|100| I met the professor lately. 

Please enter the student ID: 2022333474

please enter the feedback: You did a great job.

</aside>

> **1-7 Log Out**
> 

Return to Startup Menu

---

# **2. Student**

<aside>

=== Student Menu ===

1. Show  my report card
2. Show the overall rank, average, mid, min, max score
3. Show the certain subject rank, avg, mid, min, max
4. Send an opinion to the instructor
5. Log Out
</aside>

> **2-1 Show my report card**
> 
- Print the student’s full record

Ex) If the current logged-in student has ID 2025000111:

<aside>

2025000111|Alice|Math|90|English|100|Korean|80|90.00|A|I don't like programming|You should be more familiar with coding 

</aside>

> **2-2 Show my report card**
> 
- Print the current student's overall rank, total grade average, median, minimum, and maximum score, in order separated by spaces.
- Average must be printed to two decimal places.

`rank average median min max`

Ex)

<aside>

1 80.03 40 10 100

</aside>

> **2-3 Show the certain subject**
> 
- Get a subject input from the user.
- Print the current student's rank in that subject, subject average, median, min, and max, separated by spaces.
- Average must be printed to two decimal places.
- If no one has taken the subject print:

 “{subject_name} does not exist!\n”   ex) Math does not exist!

Ex) Please enter the subject name: Math

`rank average median min max`

10 55.34 55 40 80

Total example)

<aside>

Please enter the subject name: French

French does not exist!

</aside>

<aside>

Please enter the subject name: Korean

10 55.34 55 40 80

</aside>

> **2-4 Log-out**
> 
- Return to Startup Menu.

---

## Rules and Tips

- Be sure to match the output format exactly. Pay attention to spacing, capitalization, and line breaks.
- Use only: C Standard Library
- Keep your code clean and add comments.

---

## Submission

- **File name**: 2025XXXX_final.c (Replace XXXX with your student ID)
- Submit **one .c** file with all your code.
- **Due date**: 2025/06/16

---

## ⚠ Academic Integrity Notice

- The use of **Large Language Models (LLMs)** such as ChatGPT or similar tools to generate or assist
in writing your code may be monitored.
- If detected, **score deduction** or other academic penalties may apply.