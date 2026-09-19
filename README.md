Certificate Generator Project
Project Goal
The primary goals of this project are:

Perform Simple Data Analysis: This involves handling missing values and formatting date or text data within the dataset.
Enhance Python Concepts: Apply and reinforce various Python programming concepts.
Explore 3rd Party Libraries: Specifically, to utilize the reportlab library for PDF generation.
Overview
This project automates the generation of personalized certificates based on data from an Excel file. It processes student names, courses, course levels, and completion dates, then uses this information to create unique PDF certificates.

Steps Taken
Setup and Package Installation:

Mounted Google Drive to access project files.
Installed the reportlab library, which is essential for PDF generation.
Imported necessary libraries: numpy, pandas, and specific modules from reportlab (pagesizes, canvas, units, pdfmetrics, ttfonts).
Data Loading and Initial Exploration:

Loaded the dataset.xlsx file into a pandas DataFrame.
Performed initial inspection using df.head() and df.info() to understand data structure and identify missing values.
Data Cleaning:

Identified and addressed inconsistencies in 'Course' and 'CourseLevel' columns (e.g., varying capitalization).
Handled missing values by dropping rows with at least one empty column.
Formatted the 'Date' column from yyyy/mm/dd to dd/mm/yyyy and created a new FormattedDate column.
Removed the original 'Date' column as it was no longer needed.
Standardized 'Course' and 'CourseLevel' entries by capitalizing the first letter of each word.
Font Registration:

Defined the path to custom fonts (Lora-Bold, Lora-Regular) and registered them with reportlab for use in the certificates.
Certificate Generation Logic:

Developed a certificate_generator Python function that takes name, courseName, courseLevel, and date as input.
This function utilizes reportlab to:
Create a landscape A4 canvas.
Draw a certificate template image onto the canvas.
Place the student's name, course details, date, and a unique certificate ID (generated from a timestamp) at specific positions using the registered fonts.
Save the generated certificate as a PDF file.
Automated Certificate Creation:

Iterated through each row of the cleaned DataFrame using df.iterrows().
Called the certificate_generator function for each student, dynamically passing their respective data to create individual certificates.
Confirmed the successful generation of certificates by printing a count.
How to Use
To run this project, ensure you have the following:

Dependencies: Install reportlab:
!pip install reportlab
Dataset: An Excel file named dataset.xlsx with columns 'Name', 'Course', 'CourseLevel', and 'Date', located at /content/drive/MyDrive/certificate/1.2 Python Certificate Generator Project (STARTING TEMPLATE) 6/dataset.xlsx (or update the path in the code).
Certificate Template: An image file named certificate_template.jpg (e.g., at /content/drive/MyDrive/certificate/1.2 Python Certificate Generator Project (STARTING TEMPLATE) 6/certificate_template.jpg).
Fonts: Lora-Bold.ttf and Lora-Regular.ttf files (e.g., in a fonts subdirectory at /content/drive/MyDrive/certificate/1.2 Python Certificate Generator Project (STARTING TEMPLATE) 6/fonts).
To generate certificates:

Ensure all file paths in the notebook (for the dataset, template, and fonts) are correct and accessible.
Run all cells in sequence. The script will automatically clean the data, and then generate a PDF certificate for each valid entry in your dataset, saving them to the specified output directory.
