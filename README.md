# Interactive Resume Slideshow

This interactive slideshow showcases my resume using HTML and JavaScript.

## How to Use

1. Click the "Next" button to view the next section of the resume.
2. Click the "Previous" button to go back to the previous section.

## Resume Sections

### Education
- Brigham Young University-Idaho | Bachelor’s of Science (3.9 GPA) | Jan 2022 - Dec 2023
- Major: Data Science | Minors: Mathematics, Computer Science

### Occupational Experience
#### TA for Probability and Statistics | Brigham Young University-Idaho | Rexburg, ID | Apr 2023 - July 2023
- Tutor students one-on-one for graduate-level studies and SOA Exam P preparation
- Lead class sections in the professor’s absence

#### Data Science Consultant | Research and Business Development Center | Rexburg, ID | Jan 2023 - July 2023
- Analyze data from JIRA for 28 analytics teams at Intermountain Healthcare using Pandas and Altair
- Identify overlapping work between teams and summarize tasks/projects
- Write batch ETL processing scripts in R and Python
- Explore gasoline sale correlations using linear regression and machine learning

#### Data Analyst Intern | Onsemi | Pocatello, ID | Sep 2022 - Dec 2022
- Build a relational database for new product development in the Advanced Solutions Group
- Develop employee/user interface using MSPowerApps
- Develop RShiny web application to visualize Onsemi's global manufacturing footprint

#### Data Science Lab Tutor | Brigham Young University-Idaho | Rexburg, ID | Apr 2022 - July 2022
- Lead and assist students with assignments in R, Python, and SQL

### Projects/Volunteer Experience
#### Vasovagal Episode Study and Academic Research Paper | July 2023 - present
- Assist M.D.s in writing an academic paper based on statistical analysis of clinical data
- Identify patient attributes linked to vasovagal episodes using R and statistical analysis
- Experiment with ML models such as sci-kit learn Gradient Boosted Trees and TensorFlow Sequential Neural Networks

#### NexusTM Roommate Matching Software | Jan 2023 - present
- Implement k-nearest neighbor algorithm for personality type clustering and roommate matching in Javascript/HTML/CSS
- Build prototype as a compiled desktop application using Tkinter in Python

#### President of BYU-Idaho Data Science Society | July 2022 - December 2022
- Oversee real-world projects for approximately 100 students working with various companies

## Interactive Slideshow

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Resume Slideshow</title>
  <!-- Add your styles here if needed -->
</head>
<body>

<div id="resume">
  <div class="slide" id="slide1">
    <!-- Content for Education -->
  </div>

  <div class="slide" id="slide2">
    <!-- Content for TA Experience -->
  </div>

  <!-- Add more slides as needed -->

  <div class="slide" id="slideN">
    <!-- Content for the last section -->
  </div>

  <button onclick="prevSlide()">Previous</button>
  <button onclick="nextSlide()">Next</button>
</div>

<script>
  let currentSlide = 1;

  showSlide(currentSlide);

  function nextSlide() {
    showSlide(currentSlide += 1);
  }

  function prevSlide() {
    showSlide(currentSlide -= 1);
  }

  function showSlide(n) {
    let slides = document.getElementsByClassName('slide');

    if (n > slides.length) {
      currentSlide = 1;
    }

    if (n < 1) {
      currentSlide = slides.length;
    }

    for (let i = 0; i < slides.length; i++) {
      slides[i].style.display = 'none';
    }

    slides[currentSlide - 1].style.display = 'block';
  }
</script>

</body>
</html>

