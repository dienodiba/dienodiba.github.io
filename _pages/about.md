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
      <img src="/images/imageslider/slider-1-notext.jpg" alt="Image 1">
      <div class="slide-text-title">MT Solution</div>
      <div class="slide-text-body">Solutions for your magnetotelluric data</div>
      <div class="button-container">
        <a class="learn-more-button" href="https://dienodiba.com/MTSolutions">Learn more</a>
      </div>
    </div>
    <div class="slide">
      <img src="/images/imageslider/slider-2-notext.jpg" alt="Image 2">
      <div class="slide-text-title">FITE2DMT</div>
      <div class="slide-text-body">Fast and accurate magnetotelluric inversion</div>
      <div class="button-container">
        <a class="learn-more-button" href="https://dienodiba.com/FITE2DMT">Learn more</a>
      </div>
    </div>
    <div class="slide">
      <img src="/images/imageslider/slider-3-notext.jpg" alt="Image 3">
      <div class="slide-text-title">Journey</div>
      <div class="slide-text-body">Research highlights from field to conferences</div>
      <div class="button-container">
        <a class="learn-more-button" href="https://dienodiba.com/journey">Discover now</a>
      </div>
    </div>
    <div class="slide">
      <img src="/images/imageslider/slider-4-notext.jpg" alt="Image 4">
      <div class="slide-text-title">About Me</div>
      <div class="slide-text-body">Geophysics PhD student at University of Tokyo</div>
      <div class="button-container">
        <a class="learn-more-button" href="https://dienodiba.com/profile">View my profile</a>
      </div>
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

// Touch control
let startX = 0;
let endX = 0;

function handleSwipe() {
  const sliderContainer = document.querySelector('.image-slider');
  
  sliderContainer.addEventListener('touchstart', function(e) {
    startX = e.changedTouches[0].screenX;
  });

  sliderContainer.addEventListener('touchend', function(e) {
    endX = e.changedTouches[0].screenX;
    const diffX = startX - endX;

    if (Math.abs(diffX) > 30) { // Minimum swipe distance
      if (diffX > 0) {
        // Swipe left
        slides[currentIndex].checked = false;
        currentIndex = (currentIndex + 1) % totalSlides;
        slides[currentIndex].checked = true;
      } else {
        // Swipe right
        slides[currentIndex].checked = false;
        currentIndex = (currentIndex - 1 + totalSlides) % totalSlides;
        slides[currentIndex].checked = true;
      }
      resetSlider(currentIndex);
    }
  });
}

handleSwipe();
</script>
