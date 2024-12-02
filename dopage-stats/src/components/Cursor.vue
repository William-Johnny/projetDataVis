<script setup>
import { onMounted } from 'vue';
</script>

<template>
    <div class="slider-container">
        <input type="range" class="slider" value="0">
        <div id="description">
            <p>Conso. faible</p>
            <p>Conso. exessive</p>
        </div>
    </div>
</template>

<style>
/* General styling */
body {
  background-color: #1e1e1e;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

#description{
    display: flex;
    justify-content: space-between;
}

.slider-container {
  position: relative;
  width: 300px;
}

/* Slider base */
.slider {
  -webkit-appearance: none;
  width: 100%;
  height: 10px;
  background: linear-gradient(to right, lightblue, blue);
  outline: none;
  margin: 0;
  position: relative;
  z-index: 1;
}

/* Remove default slider thumb */
.slider::-webkit-slider-thumb {
    background-color: limegreen;
    border: 5px solid rgba(173, 255, 47, 0.6); /* Glow effect */
    border-radius: 50%;
    pointer-events: none; /* Prevent direct interaction */
    box-shadow: 0 0 10px rgba(173, 255, 47, 0.6);
}

.slider::-moz-range-thumb {
    background-color: limegreen;
    border: 5px solid rgba(173, 255, 47, 0.6); /* Glow effect */
    border-radius: 50%;
    pointer-events: none; /* Prevent direct interaction */
    box-shadow: 0 0 10px rgba(173, 255, 47, 0.6);
}

/* Custom slider thumb */
.slider-thumb {
  position: absolute;
  top: 50%;
  left: 0;
  transform: translate(-50%, -50%);
  width: 30px;
  height: 30px;
  background-color: limegreen;
  border: 5px solid rgba(173, 255, 47, 0.6); /* Glow effect */
  border-radius: 50%;
  pointer-events: none; /* Prevent direct interaction */
  box-shadow: 0 0 10px rgba(173, 255, 47, 0.6);
  z-index: 2;
}

/* Sync thumb position with slider */
.slider:active + .slider-thumb, 
.slider:focus + .slider-thumb {
  box-shadow: 0 0 15px rgba(173, 255, 47, 0.8);
}

.slider::-webkit-slider-runnable-track {
  cursor: pointer;
}

.slider-container input[type="range"] {
  position: relative;
  z-index: 1;
}

/* JavaScript interaction */
.slider-container .slider-thumb {
  pointer-events: none;
}

</style>

<script>
    onMounted(()=>{
        const slider = document.querySelector('.slider');
        const thumb = document.querySelector('.slider-thumb');
      
        slider.addEventListener('input', () => {
          const sliderValue = slider.value;
          const max = slider.max || 100;
          const min = slider.min || 0;
          const percentage = ((sliderValue - min) / (max - min)) * 100;
      
          thumb.style.left = `calc(${percentage}% - 15px)`; // Center the thumb
        });
    });
</script>