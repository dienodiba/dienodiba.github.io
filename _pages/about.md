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
    <div class="slider-images">
      <div class="slide" id="s1">
        <img src="/images/slide1.jpg" alt="Slide 1">
      </div>
      <div class="slide" id="s2">
        <img src="/images/slide2.jpg" alt="Slide 2">
      </div>
      <div class="slide" id="s3">
        <img src="/images/slide3.jpg" alt="Slide 3">
      </div>
    </div>
  </div>

  <!-- Dots for Navigation -->
  <div class="slider-dots">
    <label class="dot" for="slide1"></label>
    <label class="dot" for="slide2"></label>
    <label class="dot" for="slide3"></label>
  </div>
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
