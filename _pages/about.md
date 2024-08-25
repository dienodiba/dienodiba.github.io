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

let startX = 0;
let endX = 0;
let isTouching = false;

function goToSlide(index) {
  slides[currentIndex].checked = false;
  currentIndex = (index + totalSlides) % totalSlides;
  slides[currentIndex].checked = true;
}

// Automatic sliding
let slideInterval = setInterval(() => {
  goToSlide(currentIndex + 1);
}, 5000);

// Touch event handlers
const sliderContainer = document.querySelector('.slider-container');

sliderContainer.addEventListener('touchstart', (e) => {
  isTouching = true;
  startX = e.touches[0].clientX;
  clearInterval(slideInterval); // Pause auto-sliding when touched
});

sliderContainer.addEventListener('touchmove', (e) => {
  if (!isTouching) return;
  endX = e.touches[0].clientX;
});

sliderContainer.addEventListener('touchend', () => {
  if (!isTouching) return;
  const threshold = 50; // Minimum swipe distance in pixels
  if (startX - endX > threshold) {
    goToSlide(currentIndex + 1); // Swipe left, go to next slide
  } else if (endX - startX > threshold) {
    goToSlide(currentIndex - 1); // Swipe right, go to previous slide
  }
  isTouching = false;
  slideInterval = setInterval(() => {
    goToSlide(currentIndex + 1);
  }, 5000); // Restart auto-sliding
});
</script>

I’m a PhD student in Geophysics at the University of Tokyo, focusing on the development and application of the magnetotelluric (MT) method. I developed [FITE2DMT](https://dienodiba.com/FITE2DMT/), a Julia-based MT inversion code for fast and accurate data interpretation. On the side, I offer [professional supports](https://dienodiba.com/MTSolutions/) for data analysis and modeling of MT data.
 
