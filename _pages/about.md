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
  <input type="radio" name="slider" id="slide1" checked>
  <input type="radio" name="slider" id="slide2">
  <input type="radio" name="slider" id="slide3">
  
<div class="image-slider">
  <div class="slider-container">
    <img src="/images/journey/2023_tochigi/tochigi-1.jpg" class="slider-image" alt="Image 1">
    <img src="/images/journey/2023_tochigi/tochigi-2.jpg" class="slider-image" alt="Image 2">
    <img src="/images/journey/2023_tochigi/tochigi-3.jpg" class="slider-image" alt="Image 3">
  </div>
  <button class="prev" onclick="prevSlide()">&#10094;</button>
  <button class="next" onclick="nextSlide()">&#10095;</button>
</div>

<script>
let currentIndex = 0;

function showSlide(index) {
  const slides = document.querySelectorAll('.slider-image');
  if (index >= slides.length) currentIndex = 0;
  if (index < 0) currentIndex = slides.length - 1;
  
  slides.forEach((slide, i) => {
    slide.style.display = i === currentIndex ? 'block' : 'none';
  });
}

function nextSlide() {
  showSlide(++currentIndex);
}

function prevSlide() {
  showSlide(--currentIndex);
}

// Initialize slider
showSlide(currentIndex);
</script>
