# Data Analysis Portfolio
## Introduction
Hello!

Welcome to my Data Analyst Project Portfolio! 

I am a data analyst with experience using real-time data to foster informative decisions based on patterns and trends. I am proficient in Python, SQL, Excel, and PowerBI while currently learning Tableau and polishing off my skills in Python libraries such as Pandas and Matplotlib.

Below, I will showcase projects that display my data analysis skills and my process of extracting, cleaning, analyzing, and visualizing the datasets.

## CSULB Student Review's Sentiment Analysis 
## Repo: https://github.com/csulb-datascience/Sentiment-Analysis-for-RateMyProfessor
### Summary

The goal of this project was to extract all reviews of professors at California State University Long Beach from 1999-2023 and find out which attributes (grade, quality rating, etc.) correlated to positive or negative student reviews analyzed by each college. After the reviews were collected and the dataset was cleaned, sentiment analysis was performed on each review to classify each review as negative, neutral, or positive. Conclusions and visualizations were created which I will expand in more detail about the complete process below.

After producing line plots and box plots with t-tests, I found that for some colleges (not all our shown below) there is a relationship between COVID and online courses and lower reviews of quality and more negative reviews.

### Conclusion

Based off my findings I conclude that online learning platforms may not be effective for certain colleges and courses. A business or educational institution may want to focus more resources into improving their user experience and provide better student support for future online learning courses.

<p align="center">
  <img src="https://github.com/user-attachments/assets/a4185b69-8e36-4a1f-ae7e-b16dc209e670" alt="Description of image" width="45%" style="display: inline-block;">
  <img src="https://github.com/user-attachments/assets/618e5224-f0bf-4a20-9eb2-13b901538e41" alt="Description of image" width="45%" style="display: inline-block;">
</p>

Below, the p-values are both less than 0.05 which means I can reject the null hypothesis (there is no relationship between the student's quality ratings before and during online courses) and the more negative reviews during COVID-19 are significantly significant.

<table align="center">
  <tr>
    <td align="center">
      TValue | DF | PValue <br>
      --- | --- | --- <br>
      3.43 | 2231 | 0.001
    </td>
    <td align="center" style="width: 50%;"></td> <!-- Spacer -->
    <td align="center">
      TValue | DF | PValue <br>
      --- | --- | --- <br>
      2.36 | 3345 | 0.019
    </td>
  </tr>
</table>

<p align="center">
  <img src="https://github.com/user-attachments/assets/591658f4-a92a-4300-8573-5312ec18128a" alt="Description of image" width="45%" style="display: inline-block;">
  <img src="https://github.com/user-attachments/assets/cc5b1ba8-6a35-499a-8cc1-d420a350e000" alt="Description of image" width="45%" style="display: inline-block;">
</p>

### Challenges

The most significant challenge I faced was after collecting all the reviews, I noticed that the same professor would have more than one entry because students either mispelled their name or they taught courses in slightly different departments. To resolve this issue, I combined two string distance metrics (Levenshtein and Jaro-Winkler) to perform name matching (done in Python) and create a mapping table (a CSV manipulated in Excel) that I used to match reviews that pertained to the same professor using their instructorIDs. My mapping table consists of over 250 paired professors.

<p align="center">
  <img src="https://github.com/user-attachments/assets/a1bd5f1f-4d47-4233-ae50-f9d5c4211591" alt="Description of image" width="90%" style="display: inline-block;">
</p>

### Data Collection and Preparation

To collect the required student review data I used the following api: https://github.com/Nobelz/RateMyProfessorAPI and the Python package Selenium to extract the elements I was looking for. I used the xpath of the element on the page to tell the script what to extract and stored all these attributes and instructors in a MySQL database. I then extracted the database into a CSV for cleansing the dataset and managing it in Excel.

<p align="center">
  <img src="https://github.com/user-attachments/assets/06dbb53d-0a07-492b-a36c-74beff20baf4" alt="Description of image" width="90%" style="display: inline-block;">
</p>

To prepare my data for creating visualizations using Minitab and PowerBI I needed to organize my data by college, aggregate the dates into years and remove duplicate or mispelled majors (ex. Computer Science and ComputerScience need to be one major). To accomplish this, I created pivot tables in Excel for each college that I could use to create visualizations of the data as seen above.

### PowerBI Interactive Dashboard

Below is a dashboard I created that makes use of a slicer to give insights and analyze snapshots of the data between different dates (top right).

<p align="center">
  <img src="https://github.com/user-attachments/assets/e98d43a5-6118-4d48-ab58-75b3dc88481a" alt="Description of image" width="90%" style="display: inline-block;">
</p>
