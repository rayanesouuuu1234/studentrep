---
toc: True
comments: False
layout: post
title: College Board Quiz
description: CB quiz
type: hacks
courses: {'csp': {'week': 111}}
---
# College Board Quiz
- Score: 58/66


## Corrections

1. The code segment below is intended to swap the values of the variables first and second using a temporary variable, temp.

The block code consists of 3 lines. Line 1: temp, left arrow, first Line 2: first, left arrow, second Line 3: MISSING CODE

Which of the following can be used to replace missing code so that the code segment works as intended?

- Selected answser: second, left arrow, first

- Correct answer: second, left arrow, temp

This answer is correct because the code segment assigns the initial value of first to temp, then assigns the initial value of second to first. The initial value of first, which has been stored in temp, is then assigned to second. Therefore, the initial values of first and second have been interchanged.

5. The ticket prices at a movie theater are given below.

A table is shown with 2 columns and 4 rows. The first row of the table contains the column headers, from left to right, Type of Ticket and Price in dollars. The table is as follows: Regular, 12 Child ages 12 and below, 9 Senior ages 60 and above, 9 Below the table is the text: Additional 5 dollar fee for 3 D movies

A programmer is creating an algorithm to set the value of One word, ticket Price based on the information in the table. The programmer uses the integer  variable age for the age of the moviegoer. The Boolean variable One word, is 3 D is true when the movie is 3-D and false otherwise.

Which of the following code segments correctly sets the value of One word, ticket Price ?

- Selected answer: The block code consists of 5 lines. Some of the lines of code are indented. The code uses the variable ticket Price, closed up with initial capital P, henceforth referred to as ticket Price. Line 1: ticket Price left arrow 12 Begin block Line 2: IF begin block, begin block, age less than or equal to 12, end block, OR, begin block, age greater than or equal to 60, end block, end block Begin block Line 3, indented 1 tab: ticket Price left arrow 9 End block Line 4: ELSE Begin block Line 5, indented 1 tab: ticket Price left arrow ticket Price plus 5 End block End block

- Correct answer: The block code consists of 5 lines. Some of the lines of code are indented. The code uses the variable ticket Price, closed up with initial capital P, henceforth referred to as ticket Price. Line 1: ticket Price left arrow 12 Begin block Line 2: IF begin block, begin block, age less than or equal to 12, end block, OR, begin block, age greater than or equal to 60, end block, end block Begin block Line 3, indented 1 tab: ticket Price left arrow 9 End block End block Begin block Line 4: IF begin block is 3 D, closed up with numeral 3 and capital D, end block Begin block Line 5, indented 1 tab: ticket Price left arrow ticket Price plus 5 End block End block

This is correct b/c this code segment initially sets One word, ticket Price to 12, and then changes the price to 9 only for children and seniors. The code segment then increases One word, ticket Price by 5 for 3-D movies.

14. Consider the two programs below.

Program A: The block code consists of 4 lines. Line 1: i, left arrow, 1 Begin block Line 2: REPEAT UNTIL, begin block, i greater than 10, end block Begin block Line 3, indented 1 tab: DISPLAY, begin block, i, end block Line 4, indented 1 tab: i, left arrow, i plus 1 End block End block	Program B: The block code consists of 4 lines. Line 1: i, left arrow, 1 Begin block Line 2: REPEAT UNTIL, begin block, i greater than 10, end block Begin block Line 3, indented 1 tab: i, left arrow, i plus 1 Line 4, indented 1 tab: DISPLAY, begin block, i, end block End block End block
Which of the following best compares the values displayed by programs A and B?

- Selected answer: 
Program A and program B display identical values.

- Correct answer: Program A and program B display the same number of values, but the values differ.

This is correct b/c the programs each display ten values, but each value displayed by program B is one greater than the
corresponding value from program A. Program A displays 1 2 3 4 5 6 7 8 9 10 and program B displays  2 3 4 5 6 7 8 9 10 11.

21. The following question uses a robot in a grid of squares. The robot is represented by a triangle, which is initially facing right.

The figure shows a grid of squares with 4 columns and 8 rows. The square in the first row and third column is gray, and all other squares are white. The square in the fourth row and first column contains a right-facing triangle, representing a robot. A path of arrows shows the robot’s movement from its initial location to the gray square. The path shows the robot moving 2 squares to the right from its initial location, then 3 squares up to the gray square.

Consider the procedures below.

The block code consists of 3 lines. Begin block Line 1: PROCEDURE, Move X Times, 1 word with capital M, X, and T, begin block, x, end block Begin block Line 2, indented 1 tab: REPEAT x TIMES Begin block Line 3, indented 2 tabs: MOVE underscore FORWARD End Block End block End block The block code consists of 3 lines. Begin block Line 1: PROCEDURE, Right X Times, 1 word with capital R, X, and T, begin block, x, end block Begin block Line 2, indented 1 tab: REPEAT x TIMES Begin block Line 3, indented 2 tabs: ROTATE underscore RIGHT End block End block End block

Which of the following code segments will move the robot to the gray square?

- Selected Answer: The block code consists of 3 lines. Line 1: Move X Times, begin block, 2, end block Line 2: Right X Times, begin block, 1, end block Line 3: Move X Times, begin block, 3, end block

- Correct Answer: The block code consists of 3 lines. Line 1: Move X Times, begin block, 2, end block Line 2: Right X Times, begin block, 3, end block Line 3: Move X Times, begin block, 3, end block

This is correct b/c this code segment moves the robot forward two squares, rotates it right three times so that the robot faces the top of the grid, and then moves the robot forward three squares to the gray square.

22. A student is creating a procedure to determine whether the weather for a particular month was considered very hot. The procedure takes as input a list containing daily high temperatures for a particular month. The procedure is intended to return true if the daily high temperature was at least 90 degrees for a majority of days in the month and return false otherwise.

The program consists of 14 lines. Begin program Line 1: PROCEDURE, one word Is Hot, open parenthesis, one word temperature List, close parenthesis Line 2: open brace Line 3: total, left arrow, 0 Line 4: counter, left arrow, 0 Line 5: FOR EACH temperature IN, one word temperature List Line 6: open brace Line 7: IF, open parenthesis, temperature is greater than or equal to 90, close parenthesis Line 8: open brace Line 9: counter, left arrow, counter plus 1 Line 10: close brace Line 11: total, left arrow, total plus 1 Line 12: close brace Line 13: RETURN, open parenthesis,  MISSING CODE, close parenthesis Line 14: close brace End program. 

Which of the following can be used to replace missing code so that the procedure works as intended?

- Selected answer: Counter, less than, 0 point 5, times, total

- Correct answer: Counter, greater than, 0 point 5, times, total

This is correct b/c this Boolean expression evaluates to true when counter (the number of temperatures greater than or equal to 90) is greater than 50% of total (the number of entries in the list).

26. The grid below contains a robot represented as a triangle, initially facing up. The robot can move into a white or gray square but cannot move into a black region.

The figure shows a grid of squares with 5 columns and 4 rows. The square in the fourth row and first column contains an upward-facing triangle, representing a robot. The first row contains all white squares. The second row contains, left to right, white, black, black, black, white. The third row contains, left to right, white, black, gray, white, white. The fourth row contains, left to right, white, black, black, black, white.

The code segment below uses the procedure One word, Goal Reached, which evaluates to true if the robot is in the gray square and evaluates to falseotherwise.

The program consists of 4 lines. Begin program Line 1: REPEAT UNTIL, open parenthesis, one word Goal Reached, open parenthesis, close parenthesis, close parenthesis Line 2: open brace Line 3: MISSING CODE Line 4: close brace End program.

Which of the following replacements for missing code can be used to move the robot to the gray square?

- Selected answer: The program consists of 5 lines. Begin program Line 1: IF, open parenthesis, CAN, underscore, MOVE, open parenthesis, forward, close parenthesis, close parenthesis Line 2: open brace Line 5: MOVE, underscore, FORWARD, open parenthesis, close parenthesis Line 3: ROTATE, underscore, RIGHT, open parenthesis, close parenthesis Line 4: close brace End program.

- Correct answer: The program consists of 5 lines. Begin program Line 1: IF, open parenthesis, CAN, underscore, MOVE, open parenthesis, right, close parenthesis, close parenthesis Line 2: open brace Line 3: ROTATE, underscore, RIGHT, open parenthesis, close parenthesis Line 4: close brace Line 5: MOVE, underscore, FORWARD, open parenthesis, close parenthesis End program.

This is correct because this code segment rotates right whenever there is an open square to the right. The robot will move forward from its initial location to the upper-left corner of the grid, then rotate right, then move forward to the upper-right corner of the grid, then rotate right, then move down two squares, then rotate right, then move forward to the gray square.

41. Grades in a computer science course are based on total points earned on a midterm exam and a final exam. The teacher provides a way for students to improve their course grades if they receive high scores on the final exam: if a student’s final exam score is greater than the student’s midterm exam score, the final exam score replaces the midterm exam score in the calculation of total points.

The table below shows two students’ scores on the midterm and final exams and the calculated total points each student earns.

A table is shown with 4 columns and 3 rows. The first row of the table contains the column headers, from left to right, Student Name, Midterm Exam Score, Final Exam Score, Total Points Calculation. The table is as follows: Khalil, 90, 80, 90 plus 80 equals 170 Josefina, 70, 90, 90 plus 90 equals 180

Khalil does better on the midterm exam than on the final exam, so his original midterm and final exam scores are added to compute his total points.
Josefina does better on the final exam than on the midterm exam, so her final exam score replaces her midterm exam score in the total points calculation.
A programmer is writing a procedure to calculate a student’s final grade in the course using the score replacement policy described. The student’s exam scores are stored in the variables One word, midterm Exam and One word, final Exam. The procedure Max, open parenthesis, a comma b returns the larger of a and b.

Which of the following could be used in the procedure to calculate a student’s total points earned in the course and store the result in the variable One word, adjusted Total ?

- Selected answer: One word, adjusted Total, left arrow, Max, open parenthesis, one word midterm Exam, comma, one word final Exam, close parenthesis

- Correct aswer: One word, adjusted Total, left arrow, Max, open parenthesis, one word midterm Exam, comma, one word final Exam, close parenthesis, plus one word final Exam

This is correct b/c this expression uses theMax procedure to replace the midterm score with the higher of the two scores. The selected value is then added to the final exam score and assigned to One word, adjusted Total.

56. Consider the following program.

The block code consists of 6 lines. Line 1: count, left arrow, 1 Line 2: sum, left arrow, zero Begin block Line 3: REPEAT 10 TIMES Begin block Line 4, indented 1 tab: sum, left arrow, sum plus count Line 5, indented 1 tab: count, left arrow, count plus 2 End block End block Line 6: DISPLAY, begin block, sum, end block

Which of the following describes the result of executing the program?

- Selected answer: The program displays the sum of the even integers from 0 to 20.

- Correct answer: The program displays the sum of the odd integers from 1 to 19.

This is correct b/c the value of count starts at 1 and increases by twos, so it counts odd integers. The loop iterates 10
times, adding each intermediate value of count each time. Therefore, the program displays the sum of the odd integers starting at 1 and ending at 19.

57. A program contains the following procedures for string manipulation.

A table is shown with 2 columns and 3 rows. The first row of the table contains the column headers, from left to right, Procedure Call and Explanation. The table is as follows: Concat, open parenthesis, s t r 1 comma s t r 2, close parenthesis, Returns a single string consisting of s t r 1 followed by s t r 2. For example, Concat, open parenthesis, quotation mark, key, quotation mark, comma, quotation mark, board, quotation mark, close parenthesis, returns, quotation mark, keyboard, quotation mark. Substring, open parenthesis, s t r, comma, start, comma, length, close parenthesis, Returns a substring of consecutive characters from s t r, starting with the character at position start and containing length characters. The first character of s t r is located at position 1. For example, Substring, open parenthesis, quotation mark, delivery, quotation mark, comma, 3, comma, 4, close parenthesis returns quotation mark, live, quotation mark.

Which of the following expressions can be used to generate the string Open quotation, Happy, close quotation?

- Selected answer: Concat, open parenthesis, Substring, open parenthesis, open quotation, Harp, close quotation, comma 1 comma 1, close parenthesis, comma, Substring, open parenthesis, open quotation, Puppy, close quotation, comma, 2 comma 4, close parenthesis, close parenthesis

- Correct answer: Concat, open parenthesis, Substring, open parenthesis, open quotation, Harp, close quotation, comma 1 comma 2, close parenthesis, comma, Substring, open parenthesis, open quotation, Puppy, close quotation, comma, 3 comma 3, close parenthesis, close parenthesis

This is correct b/c this expression concatenates the first two letters of Open quotation, Harp, close quotation with the last three letters of Open quotation, puppy, close quotation, resulting
in Open quotation, Happy, close quotation.