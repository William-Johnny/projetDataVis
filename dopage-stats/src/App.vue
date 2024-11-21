<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { gsap } from 'gsap'
import { onMounted } from 'vue';
import Button from '@/components/Button.vue';
import Footer from '@/components/Footer.vue';

onMounted(()=>{
  document.querySelectorAll(".video").forEach((vid) => vid.muted = true);
  
  let tl = gsap
    .timeline()
    .to("#video", { duration: 0, opacity: 0, onComplete: () => {const element = document.getElementById("video"); element.remove();}},15)
    .to("#stop", { duration: 0, opacity: 1 },15)
    .to("#stop", { duration: 0, opacity: 0 },17)

    .to("#p1",{duration: 1, opacity: 1, y: '-50'},18)
    .to("#p1",{duration: 1, opacity: 0, y: '-150'},22)
    .to("#p2",{duration: 1, opacity: 1, y: '-50'},">")
    .to("#p2",{duration: 1, opacity: 0, y: '-150'},">4")
    
    .to("#q1",{duration: 1, opacity: 1, y: '-50'},">")

  document.querySelectorAll(".test").forEach(function(btn) {
    btn.addEventListener("click", function() {
      let tl = gsap
        .timeline()
        .to("#q1",{duration: 1, opacity: 0, y: '-150'})
        .to("#q2",{duration: 1, opacity: 1, y: '-50'})
    });
  });
  document.querySelectorAll("#test2").forEach(function(btn) {
    btn.addEventListener("click", function() {
      let tl = gsap
        .timeline()
        .to("#q2",{duration: 1, opacity: 0, y: '-150'})
        .to("#q3",{duration: 1, opacity: 1, y: '-50'})
    });
  });
  document.querySelectorAll("#test3").forEach(function(btn) {
    btn.addEventListener("click", function() {
      let tl = gsap
        .timeline()
        .to("#q3",{duration: 1, opacity: 0, y: '-150'})
        .to('#noShame', { duration: 1, opacity: 1, y: '-75' })
        .to('#isolation', { duration: 1, opacity: 1, y: '-35' })
        // .to('#guys', { duration: 0, opacity:1 })
        // .to('.guy', { duration: 1, opacity: 1, stagger: 1 },"<")
        // .to('#guys', { backgroundColor: "white"},">")
        // .to('.guy', {  opacity: 1,onComplete: () => {
        //   console.log("ok");
        //   const img = document.getElementsByClassName("guy");
        //   img.src = "@/assets/guyTransparent.png";
        //             }},"<")
        // .to("#loading", {
        //   duration: 5, // Time to fill the bar
        //   width: "100%", // Animates the width from 0% to 100%
        //   backgroundColor: "green", // Changes the color from white to green
        //   ease: "power1.inOut",
        //   onComplete: () => {
        //     console.log("Loading Complete!"); // Optional: Action after loading is complete
        //   }
        // });
        .to('#testImg', { duration: 0, opacity: 1})
    });
  });
});
</script>

<template>

  <video id="video" autoplay muted>
    <source src="@/assets/intro.mp4" type="video/mp4">
  </video> 

  <p class="phrase" id="stop">STOP !</p>

  <div class="question" id="p1" >
    <p>Toi aussi t'as l'impression que c’est tout le temps la même chose ?</p>
  </div>

  <div class="question" id="p2" >
    <p>Soit ci, soit ça, fait ci, fait ça, devient plus beau, plus grand, plus fort...</p>
  </div>

  <div class="question" id="q1" >
    <p>Pour commencer, es-tu...</p>
    <Button class="test" title="Une femme" @click="handleClick"/>
    <Button class="test" title="Un homme"  @click="handleClickMan"/>
    <Button class="test" title="Autre"/>
  </div>

  <div class="question" id="q2" >
    <p>As tu déjà eu un ou plusieurs complexes par rapport à ton physique ?</p>
    <Button id="test2" title="Oui"/>
    <Button id="test2" title="Non"/>
  </div>

  <div class="question" id="q3" >
    <p>Compares tu ton physique à celui de quelqu’un d’autre ?</p>
    <Button id="test3" title="Souvent"/>
    <Button id="test3" title="Rarement"/>
  </div>

  <div class="wrapper">
    <HelloWorld msg="You did it!" />
  </div>

  <p class="phrase" id="noShame">PAS DE HONTE !</p>
  <p  id="isolation">Tu n’es pas un cas isolé.</p>


  <div id="guys">
    <div id="loading"></div>
    <img class="guy" src="@/assets/guy.png" alt="">
    <img class="guy" src="@/assets/guy.png" alt="">
    <img class="guy" src="@/assets/guy.png" alt="">
    <img class="guy" src="@/assets/guy.png" alt="">
    <img class="guy" src="@/assets/guy.png" alt="">
    <img class="guy" src="@/assets/guy.png" alt="">
  </div>

  <div id="celebs">
    <img class="celeb" src="@/assets/202.png" alt="">
    <img class="celeb" src="@/assets/204.png" alt="">
    <img class="celeb" src="@/assets/205.png" alt="">
    <img class="celeb" src="@/assets/459.png" alt="">
  </div>

  <!-- <Footer /> -->
</template>

<script>
export default {
  methods: {
    handleClick() {
      alert("Woman");
    },
    handleClickMan() {
      alert("Man");
    },
  },
};
</script>


<style scoped>

@font-face {
  font-family: "Baloo 2";
  src:
    url("@/assets/Baloo_2,Inter/Baloo_2/static/Baloo2-ExtraBold.ttf");
}

#video{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: auto;
  height: 100%;
}

.celeb{
  width: 100px;
  height: auto;
  margin: 10px;
}

#celebs{
  width: 250px;
  display: flex;
  flex-wrap: wrap;
  position: relative;
  top: 750px;
}

#loading{
  width: 0%;
  height: 100%;
  background-color: #10EC00;
  position: absolute;
  height: 50px;
}

#testDiv{
  background-color: black;
  width: 100px;
  height: 100px;
}

#guys{
  opacity: 0;
  width: 100%;
  height: 50px;
}

.guy{
  opacity: 0;
  width: auto;
  height: 50px;
  position: relative;
  z-index: 2;
}

.question{
  opacity: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, calc(-50% + 100px));
  color: white;
  text-align: center;
  width: 260px;
}

#noShame{
  transform: translate(-50%, calc(-50% + 150px));
  font-size: xx-large;
  width: 225px;
}

#isolation{
  opacity: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, calc(-50% + 125px));
  color: white;
  text-align: center;
}

.phrase{
  opacity: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: #10EC00;
  font-size: xxx-large;
  font-family: "Baloo 2";
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}
</style>
