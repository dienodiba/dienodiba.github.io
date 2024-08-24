---
permalink: /
# title: Home
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

<!-- Image Slider -->
<div class="slider-container">
  <div class="mySlides fade">
    <img src="/images/journey/2023_iugg/iugg-1.jpg" style="width:100%;">
  </div>

  <div class="mySlides fade">
    <img src="/images/journey/2023_iugg/iugg-2.jpg" style="width:100%;">
  </div>

  <div class="mySlides fade">
    <img src="/images/journey/2023_iugg/iugg-5.jpg" style="width:100%;">
  </div>

  <div class="dot-container">
    <span class="dot" onclick="currentSlide(1)"></span> 
    <span class="dot" onclick="currentSlide(2)"></span> 
    <span class="dot" onclick="currentSlide(3)"></span> 
  </div>
</div>

<script>
let slideIndex = 0;
showSlides();

function showSlides() {
  let i;
  let slides = document.getElementsByClassName("mySlides");
  let dots = document.getElementsByClassName("dot");
  for (i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";  
  }
  slideIndex++;
  if (slideIndex > slides.length) {slideIndex = 1}    
  for (i = 0; i < dots.length; i++) {
    dots[i].className = dots[i].className.replace(" active", "");
  }
  slides[slideIndex-1].style.display = "block";  
  dots[slideIndex-1].className += " active";
  setTimeout(showSlides, 2000); // Change image every 2 seconds
}

function currentSlide(n) {
  slideIndex = n;
  showSlides();
}
</script>
