# Project 1: Standardized Test Analysis

### Overview

The first module of DSI092021 covered the following topics:

- Basic statistics and probability
- Many Python programming concepts
- Programmatically interacting with files and directories
- Visualizations
- EDA
- Working with Jupyter notebooks for development and reporting

At this point in the course I have a dilettante's understandings of these topics but have attempted to synthesize my understanding of them in order to produce a Standardized Test Analysis based SAT and ACT test data. As expressed in the assignment's README.md, "The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university." As someone who once studied for the SAT I wondered, do students perform better in subjects they prefer? Do STEM students perform better on Math and vice-versa for non-STEM students?

While I am personally familiar with the SAT, I have no personal experience with the ACT: based on my past experiences I decided to examine whether or not a student's intended college major had any impact on their SAT performance. Supposing I was a tutor or instructor for an SAT class, if I knew that STEM students performed better on the Math portion of the SAT and worse on the Reading portion, wouldn't I be a better instructor if I addressed those students' problem areas? 

My 'Problem Statement' which directed my research was: 'Positing we were starting a new tutoring service for the SAT and we wanted to make our service specialized: can we position ourselves as experts for tutoring potential STEM students? Looking at whether or not students with intended college major in a STEM degree on the SAT, the SAT reading section, the SAT math section; could we make reasonable conclusions on which topics to tutor to for those STEM students?' My loose grasp of Python left me hesitant to try a more complicated hypothesis for the data given. 

As directed, the following deliverables will be provided for this project: 

- A Jupyter notebook that describes your data with visualizations & statistical analysis.
- A README markdown file (this file) the provides an introduction to and overview of your project.
- A presentation slideshow rendered as a .pdf file. 

### Details & Code

Working through the 'starter-code.ipynb' I was able to establish a solid basis for this first project, Standardized Test Analysis. Part 1 involved declaring a problem statement, which is outlined above, as well as background research for the related topic. The majority of external documentation I looked through was provided by either the College Board, who administer the SAT, and the ACT, who administer the ACT. I also tried to look at demographics for age by state but had difficulty finding information on age for ages in Secondary Education. I found information on students ages 0 - 18 (https://www.kff.org/other/state-indicator/distribution-by-age/?dataView=1&currentTimeframe=0&sortModel=%7B%22colId%22:%22Location%22,%22sort%22:%22asc%22%7D) but that doesn't account for the distribution of ages or students that would be in Secondary School, taking the SAT or ACT. If I had more time I would have liked to encorporate this data into my analysis. I only got as far as generating the .csv file. 

In the process of researching my intended topic I found a study: https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.880.350&rep=rep1&type=pdf which seemed to examine a similar issue, but with further specificity to gender. This data was not available to me. I choose to use the datasets act_2019.csv, sat_2019.csv, and sat_2019_by_intended_college_major.csv to determine whether or not I would reach the same conclusion of those in the aforementioned study. Was there a negative correlation between STEM major and EDRW performance as well as a positive correlation between STEM major and Math performance? Relating back to the problem statement, if I was a tutor and had knowledge of this or another relationship within the data, I could better help my students prepare for the test.

Part 2. of Project 1 involved importing, cleaning, and synthesizing data from the datasets given. Once this was complete I had three data sets to work with, outlined below:

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|*object*| sat_act_2019 |The state in which the standardized test was taken| 
|ACT_participation_perc|*float*|sat_act_2019|The percentage of students whom participated in the ACT| 
|ACT_composite_score|*float*|sat_act_2019|The average ACT composite score| 
|SAT_participation_perc|*float*|sat_act_2019|The percentage of students who participated in the SAT| 
|SAT_evidence_based_reading_score|*int*|sat_act_2019|The average SAT Evidence Based Reading and Writing (EBRW) score| 
|SAT_math_score|*int*|sat_act_2019|The average SAT Math score| 
|SAT_total|*int*|sat_act_2019|The average SAT total score| 
|int_college_major|*object*|sat_2019_int_major|The student's intended college major| 
|number_test_takers|*object*|sat_2019_int_major|The number of students who took the SAT| 
|percent_total_test_takers|*float*|sat_2019_int_major|The percent of students for each intended college major| 
|sat_total|*int*|sat_2019_int_major|The average total SAT score| 
|reading_score|*int*|sat_2019_int_major|The average SAT EBRW score| 
|math_score|*int*|sat_2019_int_major|The average SAT Math score| 
|int_college_major|*object*|int_major_stem|A student's intended college major (STEM majors only)| 
|number_test_takers|*float*|int_major_stem|The number of students who took the SAT (STEM majors only)| 
|percent_total_test_takers|*float*|int_major_stem|The percent of students for each intended college major (STEM majors only)|
|sat_total|*int*|int_major_stem|The average total SAT score|
|reading_score|*int*|int_major_stem|The average SAT EBRW score|
|math_score|*int*|int_major_stem|The average SAT Math score|

Due to my level of comfortability with Python, I choose to produce results based on the given instructions provided in the starter code. The descriptive statistics allowed a quick overview of the data gathered:

Of all students, regardless of intended major, the mean SAT score was 1058.8 with a standard deviation of 82.45. The range of overall SAT scores was 326. For the Reading section, the average score was 535.5 with a standard deviation of 41.36. The range of Reading scores was 139. For the Math section, the average score was 523.0 with a standard deviation of 43.39. The range of Math scores was 190.

For STEM students specifically, the mean SAT score was 1116.56 with a standard deviation of 83.53. The range of overall SAT scores was 265. For the Reading section, the average score was 555.0 with a standard deviation of 35.61. The range of Reading scores was 101. For the Math section, the average score was 561.0 with a standard deviation of 49.89. The range of Math scores was 165.

Of all the different majors, regardless of whether or not it was STEM, those students who declared for Mathematics & Statistics scored the highest, across all criteria. There was not any one non-STEM major that was the lowest in all three scores: SAT total, Reading, and Math, however, those who declared for Family and Consumer Sciences/Human Sciences scored the lowest overall and on the Math section. 

