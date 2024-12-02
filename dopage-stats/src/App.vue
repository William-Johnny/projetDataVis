<script setup>
import { gsap } from 'gsap'
import { onMounted } from 'vue';
import Button from '@/components/Button.vue';
import Footer from '@/components/Footer.vue';
import Testimonies from '@/components/Testimonies.vue';
import Alternatives from '@/components/Alternatives.vue';
import Cursor from '@/components/Cursor.vue';
import objectiveFilter from '@/components/Modal.vue';
import Slider from '@/components/Slider.vue';

onMounted(()=>{

  const text = document.querySelector("#text");
  const img = document.querySelector("#img");
  const rest = document.getElementById("restOfBody");
  text.style.zIndex = "1";
  img.style.zIndex = "0";
  rest.style.marginTop="225%";

  text.addEventListener("click", (e) => {
      text.style.zIndex = "1";
      img.style.zIndex = "0";
  });

  img.addEventListener("click", (e) => {
      text.style.zIndex = "0";
      img.style.zIndex = "1";
  });

  // const men = document.getElementById('men');
  // men.addEventListener('click', () => {
  //   celebsPhotos=[]
  // });

  // const women = document.getElementById('women');
  // women.addEventListener('click', () => {
  //   celebsPhotos=[]
  // });

  document.querySelectorAll(".video").forEach((vid) => vid.muted = true);
  const el = document.querySelector("body");
  el.style.position = "fixed";
  
  let tl = gsap
    .timeline()
    .to("#video", { duration: 0, opacity: 0, onComplete: () => {const element = document.getElementById("video"); element.remove();}},15)
    .to("#stop", { duration: 0, opacity: 1 },15)
    .to("#stop", { duration: 0, opacity: 0 },17)

    .to("#p1",{duration: 1, opacity: 1, y: '-50'},18)
    .to("#p1",{duration: 1, opacity: 0, y: '-150'},22)
    .to("#p2",{duration: 1, opacity: 1, y: '-50'},">")
    .to("#p2",{duration: 1, opacity: 0, y: '-150'},">4")

    .to('#noShame', { duration: 1, opacity: 1, y: '-75' })
    .to('#isolation', { duration: 1, opacity: 1, y: '-35'})
    .to('#solo', { duration: 0, opacity: 1, onComplete: () => {
      const solo = document.getElementById("solo");
      const isolation = document.getElementById("isolation");
      const noShame = document.getElementById("noShame");
      noShame.remove();
      isolation.remove();
      solo.addEventListener('click', () => {
        const solo = document.getElementById("solo");
        solo.remove();
        let tl = gsap
        .timeline()
        .to('#iso',{duration: 0, opacity: 1, onComplete:()=>{
          const sprite = document.getElementById("iso");
          const rest = document.getElementById("restOfBody");
          const el = document.querySelector("body");
          sprite.addEventListener('click', () => {
            const element = document.getElementById("iso"); element.remove();
            rest.style.removeProperty('margin-top');
            el.style.removeProperty('position');
          });}, 
      })
      })
    }})
});
</script>

<template>

  <video id="video" autoplay muted playsinline>
    <source src="../public/assets/intro.mp4" type="video/mp4">
  </video> 

  <p class="phrase" id="stop">STOP !</p>

  <div class="question" id="p1" >
    <p>Toi aussi t'as l'impression que c’est tout le temps la même chose ?</p>
  </div>

  <div class="question" id="p2" >
    <p>Soit ci, soit ça, fait ci, fait ça, devient plus beau, plus grand, plus fort...</p>
  </div>

  <div class="wrapper">
    <HelloWorld msg="You did it!" />
  </div>

  <p class="phrase" id="noShame">PAS DE HONTE !</p>
  <p  id="isolation">Tu n’es pas un cas isolé.</p>
  <img src="`/assets/iso.gif`" alt="" id="iso"/>
  <img src="/assets/mecClignoteGif.gif" alt="" id="solo">

  <div id="restOfBody">
    <div id="balanceDiv">
      <img :src="`assets/balance.png`" alt="">
    </div>
    <div id="septUnDiv">
      <p id="septUn">71%</p>
    </div>
    <p>font “quelque chose” concernant leurs poids</p>
    <img :src="`assets/diag.gif`" alt="" class="decoration" id="diag">
    <div id="positionMskn">
      <img :src="`assets/deco.png`" alt="" class="decoration">
    </div>
    
    <Slider/>
    <div id="objectivePositionning">
      <img :src="`assets/objectives.png`" alt="">
    </div>

      <div id="bottom">
        <div id="filterBtn">
            <img :src="`/assets/objectiveFilter1.png`" alt="" class="filter" id="muscle" @click="bodyDisplayed=true"/>
            <img :src="`/assets/objectiveFilter2.png`" alt="" class="filter" id="fat" />
        </div>
        
        <div v-if="bodyDisplayed" id="bodyActivity">
          <img src="/assets/steroids.png" id="steroidsPics"/>
          <div id="objectiveChange" @click="bodyDisplayed=false">
            <p>< Changer d'objectif</p>
          </div>
          <h2>LES EFFETS DES STEROIDES ANABOLISANT SUR TON CORPS...</h2>
          <Cursor/>
          <div>
            <img :src="`assets/body.png`" v-if="bodyOrSqueleton" alt="" class="bodyImg"/>
            <img src="/assets/squeleton.png" alt="" id="squeleton" v-if="bodyOrSqueleton===false" class="bodyImg">
            <button class="custom-button" id="heartBtn" v-if="bodyOrSqueleton" @click="bodyOrSqueleton=false"></button>
            <img src="/assets/heart.png" alt="" v-if="bodyOrSqueleton===false" id="heart"/>
          </div>
        </div>
        <Testimonies/>
        <Alternatives/>
        <!-- <Footer /> -->
         <div id="footerDiv">
           <img src="/assets/footer.png" alt="" id="footer">
         </div>
      </div>
      
  </div>
  
</template>

<script>
export default {
  data(){
    return{
      bodyDisplayed: false,
      bodyOrSqueleton: true,
    }
  },
}
</script>

<style scoped>

@font-face {
  font-family: "Black Han Sans";
  src:
    url("@/assets/BlackHanSans-Regular.ttf");
}

#balanceDiv{
  width: 100%;
  display: flex;
  justify-content: start;
  padding-left: 50px;
}

#septUnDiv{
  width: 100%;
  display: flex;
  justify-content: end;
}

#septUn{
  font-family: "Black Han Sans";
  color: #10EC00;
  font-size: 100px;
  margin-right: 85px;
}

#steroidsPics{
  width: 100%;
  height: auto;
  margin-right: 50px
}

#heart{
  position: absolute;
  margin-top: -12px;
  margin-left: -411px;
  height: 646px;
  width: 477px;
}

#footerDiv{
  width: 100%;
  padding-left: 50px;
  padding-right: 50px
}

#solo{
  opacity: 0;
  height: 500px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

#footer{
  width: 100%;
  height: auto;
}

#iso{
  opacity: 0;
  height: 500px;
  width: 390px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

#diag{
  height: 400px;
  width: 500px;
}

#heartBtn{
  position: absolute;
  margin-top: 173px;
  margin-left: -213px;
}

.custom-button {
  width: 50px;
  height: 50px;
  background-color: limegreen;
  border: 10px solid rgba(173, 255, 47, 0.6);
  border-radius: 50%;
  box-shadow: 
    0 0 10px rgba(0, 0, 0, 0.9),
    0 0 15px limegreen;
  outline: none;
  cursor: pointer;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.custom-button:hover {
  transform: scale(1.1);
  box-shadow: 
    0 0 15px rgba(0, 0, 0, 1),
    0 0 20px limegreen;
}

.custom-button:active {
  transform: scale(0.95);
  box-shadow: 
    0 0 5px rgba(0, 0, 0, 0.7),
    0 0 10px limegreen;
}

#bodyActivity{
  display: flex;
  flex-direction: column;
  align-items: center;
}

.bodyImg{
  height: 560px;
  width: 350px;
}

#objectiveChange{
  background-color: #557BBD;
  padding: 10px;
  height: 48px;
  width: 198px;
}

#filterBtn{
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    margin-bottom: 50px;
}

.filter{
    width: 310px;
}

#positionMskn{
  display: flex;
  justify-content: end;
  width: 390px;
}

#objectivePositionning{
  height: 289px;;
  width: 384px;
}

.decoration{
  margin-bottom: 75px;
  margin-top: 75px;
}

#bottom{
  /* background-image: url("/assets/bgGreenPoints.png"); */
  margin-top: 50px;
  background-size: cover;
}

#video{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: auto;
  height: 100%;
}

#restOfBody{
  display: flex;
  flex-direction: column;
  align-items: center;
}

#loading{
  width: 0%;
  height: 100%;
  background-color: #10EC00;
  position: absolute;
  height: 50px;
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
  width: 290px;
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
  font-family: "Black Han Sans";
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
