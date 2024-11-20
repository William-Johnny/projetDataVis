<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { gsap } from 'gsap'
import { onMounted } from 'vue';
import Button from '@/components/Button.vue';
import Footer from '@/components/Footer.vue';

onMounted(()=>{
  document.querySelectorAll(".video").forEach((vid) => vid.muted = true);
  
  const videos = gsap.utils.toArray('.video');
  let tl = gsap
    .timeline()
    .to(videos[0], { duration: 1, opacity: 1 })
    
    .to(videos[1], { duration: 2, opacity: 1 },1)
    .to(videos[2], { duration: 2, opacity: 1 },1.5)
    .to("#videoContainer1", { duration: 20, scale: 0 },">-1")
    
    .to(videos[3], { duration: 2, opacity: 1 },"<1")
    .to(videos[4], { duration: 2, opacity: 1 },"<1.5")
    //.to(videos[5], { duration: 2, opacity: 1 })
    
    .to("#videoContainer2", { duration: 20, scale: 0 },">-1")
    .to(videos[5], { duration: 2, opacity: 1 },"<1")
    .to(videos[6], { duration: 2, opacity: 1 },"<1.5")
    .to("#videoContainer3", { duration: 20, scale: 0 },"<")
    .to(videos[7], { duration: 2, opacity: 1 },"<2")
    .to("#videoContainer4", { duration: 20, scale: 0 },"<")
    .to(videos[8], { duration: 2, opacity: 1 },"<1")
    .to(videos[9], { duration: 2, opacity: 1 },"<1.1")
    .to(videos[10], { duration: 2, opacity: 1 },"<1.3")
    
    .to(".video", { duration: 0, opacity: 0 },16)
    
    .to("#stop", { duration: 0, opacity: 1 },16)
    .to("#stop", { duration: 0, opacity: 0 },18)
    
    

    .to("#p1",{duration: 1, opacity: 1, y: '-50'},19)
    .to("#p1",{duration: 1, opacity: 0, y: '-150'},23)
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

onMounted(()=>{
  
})

const videos = gsap.utils.toArray('.video');

setTimeout(() => {
  document.querySelectorAll('video').forEach(b=>b.removeAttribute('loop'));
  document.querySelectorAll('video').forEach(b=>b.removeAttribute('autoplay'));
}, 20000);
</script>

<template>
  <div class="videoContainer" id="videoContainer1">
    <video class="video" id="one" width="auto" height="100%" autoplay loop>
    <source src="@/assets/videos/v1.mp4" type="video/mp4">
    </video> 
    <video class="video" id="two" width="auto" height="100%" autoplay loop>
      <source src="@/assets/videos/v2.mp4" type="video/mp4">
    </video> 
    <video class="video" id="three" width="auto" height="100%" autoplay loop>
      <source src="@/assets/videos/v3.mp4" type="video/mp4">
    </video> 
  </div>

  <div class="videoContainer" id="videoContainer2">
    <video class="video" id="four" width="auto" height="100%" autoplay loop>
    <source src="@/assets/videos/v4.mp4" type="video/mp4">
    </video> 
    <video class="video" id="five" width="auto" height="100%" autoplay loop>
      <source src="@/assets/videos/v5.mp4" type="video/mp4">
    </video> 
  </div>
  
  <div class="videoContainer" id="videoContainer3">
    <video class="video" id="six" width="auto" height="100%" autoplay loop>
      <source src="@/assets/videos/v6.mp4" type="video/mp4">
    </video>
    <video class="video" id="seven" width="auto" height="100%" autoplay loop>
    <source src="@/assets/videos/v7.mp4" type="video/mp4">
    </video> 
  </div>  

  <div class="videoContainer" id="videoContainer4">
    <video class="video" id="eight" width="auto" height="100%" autoplay loop>
      <source src="@/assets/videos/v8.mp4" type="video/mp4">
    </video> 
    <video class="video" id="nine" width="auto" height="100%" autoplay loop>
      <source src="@/assets/videos/v9.mp4" type="video/mp4">
    </video> 
    <video class="video" id="ten" width="auto" height="100%" autoplay loop>
      <source src="@/assets/videos/v10.mp4" type="video/mp4">
    </video> 
    <video class="video" id="eleven" width="auto" height="100%" autoplay loop>
      <source src="@/assets/videos/v11.mp4" type="video/mp4">
    </video>
  </div>

  <p class="phrase" id="stop">STOP !</p>

  <div class="question" id="p1" >
    <p>Toi aussi t'as l'impression que c’est tout le temps la même chose ?</p>
  </div>

  <div class="question" id="p2" >
    <p>Soit ci, soit ça, fait ci, fait ça, devient plus beau, plus grand, plus fort...</p>
  </div>

  <div class="question" id="q1" >
    <p>Pour commencer, es-tu...</p>
    <Button class="test" title="Une femme"/>
    <Button class="test" title="Un homme"/>
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


<style scoped>

@font-face {
  font-family: "Baloo 2";
  src:
    url("@/assets/Baloo_2,Inter/Baloo_2/static/Baloo2-ExtraBold.ttf");
}

.celeb{
  width: 100px;
  height: auto;
  margin: 10px;
}

.videoContainer{
  position: absolute;
  top: 0px;
  left: 0px;
  height: 100%;
  width: 100%;
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
  transform: translate(-50%, calc(-50% + 125px));
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

#one{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

#two{
  position: absolute;
  top: 121%;
  left: 1%;
  transform: translate(-50%, -50%);
  z-index: 1;
}

#three{
  position: absolute;
  top: -24%;
  left: 99%;
  transform: translate(-50%, -50%);
  z-index: 2;
}

#four{
  position: absolute;
  top: 10%;
  left: 10%;
  transform: translate(-50%, -50%);
  z-index: 3;
}

#five{
  position: absolute;
  top: 90%;
  left: 90%;
  transform: translate(-50%, -50%);
  z-index: 4;
}

#six{
  position: absolute;
  top: -4%;
  left: 84%;
  transform: translate(-50%, -50%);
  z-index: 9;
}

#seven{
  position: absolute;
  top: 103%;
  left: 10%;
  transform: translate(-50%, -50%);
  z-index: 5;
}

#eight{
  position: absolute;
  top: 80%;
  left: 13%;
  transform: translate(-50%, -50%);
  z-index: 6;
}

#nine{
  position: absolute;
  top: 110%;
  left: 91%;
  transform: translate(-50%, -50%);
  z-index: 7;
}

#ten{
  position: absolute;
  top: 3%;
  left: 11%;
  transform: translate(-50%, -50%);
  z-index: 8;
}

#eleven{
  position: absolute;
  top: 10%;
  left: 80%;
  transform: translate(-50%, -50%);
  z-index: 8;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

.video {
  display: block;
  opacity: 0;
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

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .video {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
