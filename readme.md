HOW TO EXECUTE THE EXAM SEATING & ATTENDANCE AUTOMATION SYSTEM
================================================================

1. PREREQUISITES
-----------------
   - Docker Desktop must be installed and running on your machine.
   - You do not need to install Python or any libraries manually; Docker handles everything.

2. PROJECT SETUP
-----------------
   Before running the program, ensure your folder contains the following:

   A. Files:
      - input_data_tt.xlsx        (The main input Excel file with timetable, students, and rooms)
      - seating_logic.py          (Python script for Seating Arrangement)
      - attendance_generator.py   (Python script for Attendance Sheets)
      - Dockerfile                (Configuration for building the environment)
      - docker-compose.yml        (Configuration for running the services)

   B. Folders:
      - photos/                   (A folder containing student images)
          |-- nopic.jpg           (REQUIRED: A placeholder image for missing photos)
          |-- [RollNo].jpg        (Student images, e.g., 1101CS01.jpg)

3. HOW TO RUN
--------------
   1. Open your terminal (Command Prompt, PowerShell, or Terminal).
   2. Navigate to this project folder.
   3. Run the following command:

      docker-compose up --build

   4. Wait for the process to complete. You will see logs in the terminal indicating:
      - "Checking for clashes..."
      - "Allocating [Course]..."
      - "Generating Output Files..."
      - "Starting PDF Generation..."

4. OUTPUTS
-----------
   Once the program finishes, the following files will appear in your project folder:

   1. op_overall_seating_arrangement.xlsx
      - The master Excel file containing the complete seating plan.

   2. [Date]_[Session] folders (e.g., 2025-11-22_Morning)
      - Folders containing individual Excel seating plans for each room.

   3. Attendance_Sheets folder
      - A folder containing PDF attendance sheets for every room and course.

5. TROUBLESHOOTING
-------------------
   - Error: "error during connect: ... The system cannot find the file specified."
     Solution: Make sure Docker Desktop is open and running (Green icon).

   - Error: "CRITICAL ERROR: No allocations generated."
     Solution: Check your input_data_tt.xlsx. Ensure the 'in_course_roll_mapping' sheet has the correct column names ('course_code' and 'rollno').

   - Error: "nopic.jpg not found"
     Solution: Ensure you have placed a dummy image named 'nopic.jpg' inside the 'photos' folder.

================================================================

