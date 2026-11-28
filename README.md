1. What langscore does:
This package reads student language test scores and outputs
    basic statistics based on category of performance. Designed for a
    language instructor who works with students on an individual basis or 
    in small group settings, maintaining a weekly record of each student's
    performance across core competencies over time in order to tailor
    instruction to each individual's strengths and weaknesses in
    preparation for a formal language proficiency test such as the Oral
    Proficiency Interview (OPI).

Functions:

    read_scores() — reads the CSV of a student’s scores
    clean_scores() — drops incomplete rows
    filter_student() — returns only the rows for a chosen student
    section_summary() — returns mean, median, and range by section
    make_score_set() — builds the S3 score_set object
    plot_scores() — draws the boxplot by core competency

2. How to install:
devtools::install_github("adbrinton/langscore")

3. Example:
library(langscore)

scores <- read_scores("student_scores.csv")
scores <- clean_scores(scores)
one_student <- filter_student(scores, "Alex Rivera")  # use a name from the file
summary_df <- section_summary(one_student)
ss <- make_score_set(one_student, summary_df)
print(ss)
plot_scores(ss)

4. AI use statement:
ChatGPT was used to generate sample data for student_scores.csv
