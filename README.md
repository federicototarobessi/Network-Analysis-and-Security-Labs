GYMLOG
#### Video Demo:  https://youtu.be/wHeMz7BpyCw
#### Description:
Overview

Gymlog is a web-based fitness tracking application developed as my final project for CS50. The goal of the project is to provide users with a simple but structured way to create training programs, log their workouts, and review their progress over time. Unlike generic note-based workout tracking, Gymlog focuses on repeatability and clarity: programs are defined once, workouts are executed based on those definitions, and historical data is automatically stored and visualized.
The project was built using Python, Flask, SQLite, HTML, Jinja, and Bootstrap, combining concepts from CS50 such as databases, web development, authentication, and server-side logic.

Core Functionality

After registering and logging in, each user can create one or more training programs. A program represents a workout routine and contains multiple exercises. For each exercise, the user can define default parameters such as number of sets, repetitions, rest time, and starting weight.
When the user starts a workout by clicking “Train”, Gymlog automatically generates a training session based on the predefined structure of the program. The user only needs to input the repetitions completed and the weight used for each set. Once submitted, the workout is saved permanently in the database.
Gymlog also includes a detailed history section. Each workout session is stored per exercise and per set, allowing the user to review past performances. Historical data can be filtered by date range and exported as a CSV file. This makes Gymlog useful not only for daily tracking but also for long-term progress analysis.

File Structure and Explanation
app.py - This is the core of the application. It contains all Flask routes, database queries, and business logic.
Key responsibilities include:

User authentication (register, login, logout) - Session management using Flask-Session
CRUD operations for programs and exercises
Workout execution and logging
Historical data retrieval and CSV export
All routes are protected using a custom login_required decorator to ensure users can only access their own data. Database interactions are handled using CS50’s SQL library for simplicity and readability.

helpers.py - This file contains utility functions shared across the application.
It includes:

login_required: a decorator that restricts access to authenticated users
apology: a helper function to render user-friendly error messages
Separating these helpers keeps app.py cleaner and easier to maintain.

fitness.db - This SQLite database stores all persistent data for the application.
The main tables include:

users: stores user credentials (hashed passwords)
programs: stores training programs linked to users
program_exercises: stores exercises and default parameters
exercise_logs: stores workout data per session, per exercise, and per set
The database schema was designed to avoid redundancy and to support future extensions, such as advanced statistics.

Templates (templates/)

All HTML files use Jinja templating and extend a shared base layout.

layout.html - The base template that defines the overall page structure, navigation bar, and Bootstrap imports.
login.html and register.html - Handle user authentication with consistent styling and validation feedback.
index.html - Displays the list of training programs belonging to the logged-in user.
program_detail.html - Shows all exercises within a program and allows editing or deleting them.
train_program.html - Generates the workout interface dynamically, showing the correct number of sets per exercise.
program_history.html - Displays workout history, grouped by exercise and date, with optional filters and graphs.
Each template focuses on a single responsibility to keep the frontend modular and readable.

Design Decisions

One important design choice was separating program definition from workout execution. Programs define structure, while workouts log performance. This mirrors real-world training habits and avoids repeatedly redefining the same exercises.
Another key decision was storing workout data at the set level instead of just per exercise. While this increases database complexity, it allows for more accurate tracking and future expansion (e.g., volume calculations or progression charts).
Bootstrap was chosen for styling to ensure a clean, responsive interface without spending excessive time on custom CSS. The visual style prioritizes readability and usability over excessive decoration.

Conclusion

Gymlog combines multiple concepts taught throughout CS50 into a cohesive and practical application. It demonstrates database design, user authentication, server-side logic, and dynamic web interfaces. The project is intentionally extensible and could be expanded in the future with features such as progress analytics, exercise libraries, or mobile optimization.
Overall, Gymlog represents both my technical growth during CS50 and my interest in building software that solves real-world problems in a structured and thoughtful way.
