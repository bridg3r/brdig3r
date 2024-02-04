<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Resume Slideshow</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      background-color: #f0f0f0;
    }

    #resume {
      width: 60%;
      max-width: 800px;
      overflow: hidden;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
      border-radius: 10px;
    }

    .slide {
      display: none;
      padding: 20px;
    }

    button {
      padding: 10px;
      margin: 10px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background-color: #45a049;
    }
  </style>
</head>
<body>

<div id="resume">
  <div class="slide" id="slide1">
    <h2>Education</h2>
    <p>Brigham Young University-Idaho | Bachelor’s of Science (3.9 GPA) | Jan 2022 - Dec 2023</p>
    <!-- Add more details if needed -->
  </div>

  <div class="slide" id="slide2">
    <h2>Occupational Experience</h2>
    <p>TA for Probability and Statistics | Brigham Young University-Idaho | Rexburg, ID | Apr 2023 - July 2023</p>
    <!-- Add more details if needed -->
  </div>

  <!-- Add more slides as needed -->

  <div class="slide" id="slideN">
    <h2>Projects/Volunteer Experience</h2>
    <p>Vasovagal Episode Study and Academic Research Paper | July 2023 - present</p>
    <!-- Add more details if needed -->
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

