---
permalink: /
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
  <input type="radio" id="slide4" name="slider">
  
  <div class="slider-container">
    <div class="slide">
      <img src="/images/imageslider/slider-1.jpg" alt="Image 1">
    </div>
    <div class="slide">
      <img src="/images/imageslider/slider-2.jpg" alt="Image 2">
    </div>
    <div class="slide">
      <img src="/images/imageslider/slider-3.jpg" alt="Image 3">
    </div>
    <div class="slide">
      <img src="/images/imageslider/slider-4.jpg" alt="Image 4">
    </div>
  </div>

  <div class="slider-dots">
    <label for="slide1" class="dot"></label>
    <label for="slide2" class="dot"></label>
    <label for="slide3" class="dot"></label>
    <label for="slide4" class="dot"></label>
  </div>
</div>

<script>
let currentIndex = 0;
const slides = document.querySelectorAll('input[name="slider"]');
const totalSlides = slides.length;
let slideInterval;

function startSlider() {
  slideInterval = setInterval(() => {
    slides[currentIndex].checked = false; 
    currentIndex = (currentIndex + 1) % totalSlides; 
    slides[currentIndex].checked = true; 
  }, 5000); 
}

function resetSlider(index) {
  clearInterval(slideInterval);
  currentIndex = index;
  startSlider();
}

slides.forEach((slide, index) => {
  slide.addEventListener('change', () => resetSlider(index));
});

startSlider();
</script>

I’m a PhD student in Geophysics at the University of Tokyo, focusing on the development and application of the magnetotelluric (MT) method. I developed [FITE2DMT](https://dienodiba.com/FITE2DMT/), a Julia-based MT inversion code for fast and accurate data interpretation. On the side, I offer [professional supports](https://dienodiba.com/MTSolutions/) for data analysis and modeling of MT data.
 
