---
permalink: /
# title: Home
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

<!-- Image Slider -->
<div class="image-slider">
  <input type="radio" id="slide1" name="slider" checked>
  <input type="radio" id="slide2" name="slider">
  <input type="radio" id="slide3" name="slider">
  
  <div class="slider-container">
    <div class="slide">
      <img src="/images/journey/2023_tochigi/tochigi-1.jpg" alt="Image 1">
    </div>
    <div class="slide">
      <img src="/images/journey/2023_tochigi/tochigi-2.jpg" alt="Image 2">
    </div>
    <div class="slide">
      <img src="/images/journey/2023_tochigi/tochigi-3.jpg" alt="Image 3">
    </div>
  </div>

  <div class="slider-dots">
    <label for="slide1" class="dot"></label>
    <label for="slide2" class="dot"></label>
    <label for="slide3" class="dot"></label>
  </div>
</div>

<script>
  let currentIndex = 0;
  const slides = document.querySelectorAll('input[name="slider"]');
  const totalSlides = slides.length;

  setInterval(() => {
    slides[currentIndex].checked = false; 
    currentIndex = (currentIndex + 1) % totalSlides; 
    slides[currentIndex].checked = true; 
  }, 2000); 
</script>
