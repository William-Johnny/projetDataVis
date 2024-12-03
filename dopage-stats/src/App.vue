<script setup>
import { gsap } from 'gsap'
import { onMounted, onUpdated } from 'vue';
import Button from '@/components/Button.vue';
import Footer from '@/components/Footer.vue';
import Testimonies from '@/components/Testimonies.vue';
import Alternatives from '@/components/Alternatives.vue';
import Cursor from '@/components/Cursor.vue';
import objectiveFilter from '@/components/Modal.vue';
import Slider from '@/components/Slider.vue';
import data from '../data.json';

onUpdated(()=>{
  const slider = document.querySelector('#cursorSteBrain input');
  const bodySliderSte = document.querySelector('#cursorSte input');
  const bodySliderIns = document.querySelector('#cursorIns input');
  const image = document.querySelector('.guyDiag');
  const div = document.querySelector('#brainInfoDiv');
  const heartDiv = document.querySelector('#heartDiv');
  const heartBtn =document.querySelector("#heartBtn");
  const kidneyBtn =document.querySelector("#kidneyBtn");
  const kidneyDiv = document.querySelector('#kidneyDiv');
  const nutsBtn =document.querySelector("#nutsBtn");
  const nutsDiv = document.querySelector('#nutsDiv');

  if (heartBtn) {
    heartBtn.addEventListener('click', () => {
      heartBtn.style.opacity="0";
      heartDiv.innerHTML = `<img src="/assets/organs/heart.png" alt="" id="heart"/> <p class="info">${data.body.Insuline.coeur[0]}</p>`
      const heart = document.querySelector('#heart');
      heart.style.position="absolute";
      heart.style.marginTop="-12px";
      heart.style.marginLeft="-411px";
      heart.style.height="646px";
      heart.style.width="477px";
      const info = document.querySelector('.info');
      info.style.position="absolute";
      info.style.marginTop="300px";
      info.style.marginLeft="-300px";
    });
  }

  if (nutsBtn) {
    nutsBtn.addEventListener('click', () => {
      nutsBtn.style.opacity="0";
      nutsDiv.innerHTML = `<img src="/assets/organs/nuts.png" alt="" id="nuts" class="organs"/> <p class="info">${data.body.Stéroides_anabolisants.Testicules[0]}}</p>`
      const nuts = document.querySelector('#nuts');
      nuts.style.position="absolute";
      nuts.style.marginTop="350px";
      nuts.style.marginLeft="-235px";
      nuts.style.height="120px";
      nuts.style.width="120px";

      const info = document.querySelector('.info');
      info.style.position="absolute";
      info.style.marginTop="300px";
      info.style.marginLeft="-300px";
    });
  }

  if (kidneyBtn) {
    kidneyBtn.addEventListener('click', () => {
      kidneyBtn.style.opacity="0";
      kidneyDiv.innerHTML = `<img src="/assets/organs/kidney.png" alt="" id="kidney" class="organs" /> <p class="info">${data.body.Stéroides_anabolisants.rein[0]}</p>`
      const kidney = document.querySelector('#kidney');
      kidney.style.position="absolute";
      kidney.style.marginTop="360px";
      kidney.style.marginLeft="-235px";
      kidney.style.height="120px";
      kidney.style.width="120px";
      const info = document.querySelector('.info');
      info.style.position="absolute";
      info.style.marginTop="300px";
      info.style.marginLeft="-300px";
    });
  }

  if (bodySliderIns) {
    bodySliderIns.addEventListener('input', () => {
      if (bodySliderIns.value < 50) {
        heartDiv.innerHTML = `<img src="/assets/organs/heart.png" alt="" id="heart"/> <p class="info">${data.body.Insuline.coeur[0]}</p>`
        const info = document.querySelector('.info');
        info.style.position="absolute";
        info.style.marginTop="300px";
      info.style.marginLeft="-300px";
        const heart = document.querySelector('#heart');
        heart.style.position="absolute";
        heart.style.marginTop="-12px";
        heart.style.marginLeft="-411px";
        heart.style.height="646px";
        heart.style.width="477px";
      } else {
        heartDiv.innerHTML = `<img src="/assets/organs/heartR.png" alt="" id="heart"/> <p class="info">${data.body.Insuline.coeur[1]}</p>`
        const heart = document.querySelector('#heart');
        heart.style.position="absolute";
        heart.style.marginTop="-12px";
        heart.style.marginLeft="-411px";
        heart.style.height="646px";
        heart.style.width="477px";
        const info = document.querySelector('.info');
        info.style.position="absolute";
        info.style.marginTop="300px";
      info.style.marginLeft="-300px";
      }
    });
  }

  if (bodySliderSte) {

    bodySliderSte.addEventListener('input', () => {
      if (bodySliderSte.value < 50) {
        kidneyDiv.innerHTML = `<img src="/assets/organs/kidney.png" alt="" id="kidney" class="organs"/> <p class="info">${data.body.Stéroides_anabolisants.rein[0]}</p>`
        nutsDiv.innerHTML = `<img src="/assets/organs/nuts.png" alt="" id="nuts" class="organs"/> <p class="info">${data.body.Stéroides_anabolisants.Testicules[0]}</p>`
        const info = document.getElementsByClassName('info');
        for(let i=0; i<info.length; i++)
        {
          info[i].style["position"] = "absolute";
          info[i].style["marginTop"] = "300px";
          info[i].style["marginLeft"] = "-300px";
        }
        
        const kidney = document.querySelector('#kidney');
      kidney.style.position="absolute";
      kidney.style.marginTop="360px";
      kidney.style.marginLeft="-235px";
      kidney.style.height="120px";
      kidney.style.width="120px";

      const nuts = document.querySelector('#nuts');
      nuts.style.position="absolute";
      nuts.style.marginTop="350px";
      nuts.style.marginLeft="-235px";
      nuts.style.height="120px";
      nuts.style.width="120px";
      } else {
        kidneyDiv.innerHTML = `<img src="/assets/organs/kidneyR.png" alt="" id="kidney" class="organs"/> <p class="info">${data.body.Stéroides_anabolisants.rein[1]}</p>`
        nutsDiv.innerHTML = `<img src="/assets/organs/nutsR.png" alt="" id="nuts" class="organs"/> <p class="info">${data.body.Stéroides_anabolisants.Testicules[1]}</p>`
        
        const kidney = document.querySelector('#kidney');
      kidney.style.position="absolute";
      kidney.style.marginTop="360px";
      kidney.style.marginLeft="-235px";
      kidney.style.height="120px";
      kidney.style.width="120px";

      const nuts = document.querySelector('#nuts');
      nuts.style.position="absolute";
      nuts.style.marginTop="350px";
      nuts.style.marginLeft="-235px";
      nuts.style.height="120px";
      nuts.style.width="120px";
        
      const info = document.getElementsByClassName('info');
      for(let i=0, len=info.length; i<len; i++)
        {
          info[i].style["position"] = "absolute";
          info[i].style["marginTop"] = "300px";
          info[i].style["marginLeft"] = "-300px";
        }
      }
    });
  }
  
  if (slider) {
    slider.addEventListener('input', () => {
      if (slider.value < 50) {
        image.src = '/assets/20.png';
        div.innerHTML = "<p id='brainPercentage'>20%</p> <p id='brainTxt'>des utilisateurs notent des changements d’humeur modérés, mais non agressifs.</p>"
        const brainP = document.querySelector('#brainPercentage');
        brainP.style.fontFamily="Black Han Sans";
        brainP.style.color="#10EC00";
        brainP.style.fontSize="100px";
      } else {
        image.src = '/assets/40.png'; 
        div.innerHTML = "<p id='brainPercentage'>40%</p> <p id='brainTxt'>des utilisateurs à fortes doses mentionnent des épisodes d'irritabilité ou de comportement violent​</p>"
        const brainP = document.querySelector('#brainPercentage');
        brainP.style.fontFamily="Black Han Sans";
        brainP.style.color="#10EC00";
        brainP.style.fontSize="100px";
      }
    });
  }
})

onMounted(()=>{
  const rest = document.getElementById("restOfBody");
  rest.style.marginTop="225%";

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
        const videoElem = document.getElementById("iso");
        videoElem.play();
        const solo = document.getElementById("solo");
        solo.remove();
        let tl = gsap
        .timeline()
        .to('#iso',{duration: 0, opacity: 1, onComplete:()=>{
          const sprite = document.getElementById("iso");
          const rest = document.getElementById("restOfBody");
          const el = document.querySelector("body");
          setTimeout(() => {
            const element = document.getElementById("iso"); 
            element.remove();
            rest.style.removeProperty('margin-top');
            el.style.removeProperty('position');
            const diagVid = document.getElementById("diagVid");
            diagVid.play();
          }, 6000);
          }, 
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
  <video id="iso" class="video" muted playsinline>
    <source src="/assets/iso.mp4" type="video/mp4">
  </video> 
  <img src="/assets/mecClignoteGif.gif" alt="" id="solo">

  <div id="restOfBody">
    <div id="top"></div>
    <a href="#top" id="topElevator">
      <img src="/assets/logo.png" alt="" id="logo">
    </a>
    <video id="diagVid" class="video" muted playsinline>
      <source src="/assets/diagVid.mp4" type="video/mp4">
    </video>
    <div id="positionMskn">
      <img :src="`assets/deco.png`" alt="" class="decoration">
    </div>
    
    <Slider/>
    <div id="objectivePositionning">
      <img :src="`assets/objectives.png`" alt="">
      <h2 class="objTxt" id="so">ET DONC </h2>
      <h2 class="objTxt">QUELS SONT TES OBJECTIFS ?</h2>
    </div>

      <div id="bottom">
        <div id="filterBtn">
          <a href="#steroidsPics">
            <img :src="`/assets/objectiveFilter1.png`" alt="" class="filter" id="muscle" @click="bodyDisplayedSte=true; bodyOrSqueleton=true"/>
          </a>
          <a href="#steroidsPics">
            <img :src="`/assets/objectiveFilter2.png`" alt="" class="filter" id="fat" @click="bodyDisplayedIns=true; bodyOrSqueleton=true"/>
          </a>
        </div>
        
        <div v-if="bodyDisplayedSte" id="bodyActivity">
          <div class="bodyActivity">
            <img src="/assets/steroids.png" id="steroidsPics"/>
            <div id="objectiveChange" @click="bodyDisplayedSte=false">
              <a href="#objectivePositionning">< Changer d'objectif</a>
            </div>
            <h2 id="effects">LES EFFETS DES STEROIDES ANABOLISANT SUR TON CORPS...</h2>
            <Cursor id="cursorSte"/>
            <div>
              <img :src="`assets/body.png`" v-if="bodyOrSqueleton" alt="" class="bodyImg"/>
              <img src="/assets/squeleton.png" alt="" id="squeleton" v-if="bodyOrSqueleton===false" @click="bodyOrSqueleton=true; disappear('kidneyDiv'); disappear('nutsDiv')" class="bodyImg">
              <button class="custom-button" id="kidneyBtn" v-if="bodyOrSqueleton" @click="bodyOrSqueleton=false; appear('kidneyDiv')"></button>
              <div id="kidneyDiv"></div>
              <button class="custom-button" id="nutsBtn" v-if="bodyOrSqueleton" @click="bodyOrSqueleton=false; appear('nutsDiv')"></button>
              <div id="nutsDiv"></div>
            </div>
          </div>
          <div id="brainNumNCursor" class="bodyActivity">
            <div id="brainNum">
              <img src="/assets/20.png" class="guyDiag"/>
              <div id="brainInfoDiv">
                <p id='brainPercentage'>20%</p> 
                <p id='brainTxt'>des utilisateurs notent des changements d’humeur modérés, mais non agressifs.</p>
              </div>
            </div>
            <Cursor id="cursorSteBrain"/>
          </div>
          <div id="testimonies">
            <p id="doubt">Et si tu as encore des doutes,</p>
            <div id="rect">
                <img src="/assets/doubtRect.png" alt="" id="rectImg">
            </div>
            <img :src="`/assets/testimonies/Ins/temoignageInsuline_1recto.png`"  alt="" v-if="r5" @click="r5=false"/>
            <img :src="`/assets/testimonies/Ins/temoignageInsuline_1verso.png`"  alt="" v-if="r5===false" @click="r5=false"/>
            <img :src="`/assets/testimonies/Ins/temoignageInsuline_2recto.png`"  alt="" v-if="r6" @click="r6=false"/>
            <img :src="`/assets/testimonies/Ins/temoignageInsuline_2verso.png`"  alt="" v-if="r6===false" @click="r6=false"/>
            <img :src="`/assets/testimonies/Ins/temoignageInsuline_3recto.png`"  alt="" v-if="r7" @click="r7=false"/>
            <img :src="`/assets/testimonies/Ins/temoignageInsuline_3verso.png`"  alt="" v-if="r7===false" @click="r7=false"/>
          </div>
        </div>

        <div v-if="bodyDisplayedIns" class="bodyActivity">
          <img src="/assets/insuline.png" id="steroidsPics"/>
          <div id="objectiveChange" @click="bodyDisplayedIns=false">
            <a href="#objectivePositionning">< Changer d'objectif</a>
          </div>
          <h2 id="effects">LES EFFETS DES STEROIDES ANABOLISANT SUR TON CORPS...</h2>
          <Cursor id="cursorIns"/>
          <div>
            <img :src="`assets/body.png`" v-if="bodyOrSqueleton" alt="" class="bodyImg"/>
            <img src="/assets/squeleton.png" alt="" id="squeleton" v-if="bodyOrSqueleton===false" class="bodyImg" @click="bodyOrSqueleton=true; disappear('kidneyDiv')">
            <button class="custom-button" id="heartBtn" v-if="bodyOrSqueleton" @click="bodyOrSqueleton=false; appear('kidneyDiv')" ></button>
            <div id="heartDiv"></div>
          </div>
          <div id="testimonies">
            <p id="doubt">Et si tu as encore des doutes,</p>
            <div id="rect">
                <img src="/assets/doubtRect.png" alt="" id="rectImg">
            </div>
            <img :src="`/assets/testimonies/SA/temoignageSA_1recto.png`"  v-if="r1" @click="r1=false" alt="" />
            <img :src="`/assets/testimonies/SA/temoignageSA_1verso.png`"  v-if="r1===false" @click="r1=true" alt="" />
            <img :src="`/assets/testimonies/SA/temoignageSA_2recto.png`"  v-if="r2" @click="r2=false" alt="" />
            <img :src="`/assets/testimonies/SA/temoignageSA_2verso.png`"  v-if="r2===false" @click="r2=true" alt="" />
            <img :src="`/assets/testimonies/SA/temoignageSA_3recto.png`" v-if="r3" @click="r3=false" alt="" />
            <img :src="`/assets/testimonies/SA/temoignageSA_3verso.png`"  v-if="r3===false" @click="r3=true" alt="" />
            <img :src="`assets/testimonies/SA/temoignageSA_4recto.png`"  v-if="r4" @click="r4=false" alt="" />
            <img :src="`/assets/testimonies/SA/temoignageSA_4verso.png`"  v-if="r4===false" @click="r4=true" alt="" />
          </div>
        </div>
        <Alternatives/>
        <!-- <Footer /> -->
         <div id="footerDiv">
           <img src="/assets/footer.png" alt="" id="footer">
           <div id="creditsDiv"><a href="/assets/credits.html" id="credits">CREDITS</a></div>
         </div>
      </div>
      
  </div>
  
</template>

<script>
export default {
  data(){
    return{
      bodyDisplayedIns: false,
      bodyDisplayedSte: false,
      bodyOrSqueleton: true,
      r1: true,
      r2: true,
      r3: true,
      r4: true,
      r5: true,
      r6: true,
      r7: true
    }
  },methods: {
    appear(id) {
      const el = document.getElementById(id);
      el.style.opacity="1";
    },
    disappear(id) {
      const el = document.getElementById(id);
      el.style.opacity="0";
    },
  },
}
</script>

<style scoped>

@font-face {
  font-family: "Black Han Sans";
  src:
    url("@/assets/BlackHanSans-Regular.ttf");
}

@font-face {
  font-family: "InterLight";
  src:
    url("@/assets/Baloo_2,Inter/Inter/static/Inter_18pt-Light.ttf");
}

.info{
  position:"absolute";
  margin-top:"300px";
  margin-left:"-300px";
}

#brainTxt{
  font-family: "InterLight";
}

#creditsDiv{
  margin-top: -149px;
  margin-left: 20px;
}

#effects{
  margin-top: 50px;
  margin-bottom: 50px;
  margin-left: 20px;
}

#doubt{
    margin-bottom: 25px;
    margin-left: 50px;
    width: 100%;
}

#testimonies > img{
  height: 255px;
}

#testimonies{
  display: flex;
  flex-direction: column;
  align-items: center;
}

#diagVid{
  height: 100%;
  width: 100%;
}

#credits{
  font-family: "Black Han Sans";
  font-size: 12px;
}

#heartDiv{
  position: absolute;
  margin-top: -581px;
  margin-left: 346px;
}

#kidneyDiv{
  opacity: 0;
  position: absolute;
  margin-top: -581px;
  margin-left: 346px;
}

#nutsDiv{
  opacity: 0;
  position: absolute;
  margin-top: -581px;
  margin-left: 346px;
}

#bodyActivity{
  display: flex;
  flex-direction: column;
  align-items: center;
}

#brainPercentage{
  font-family: "Black Han Sans";
  color: #10EC00;
  font-size: 100px;
}

#brainNumNCursor{
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 300px;
  margin-top: 50px;
  margin-bottom: 50px;
}

#brainNum{
  display: flex;
  width: 100%;
  margin-bottom: 30px;
}

.guyDiag{
  height: 270px;
  width: 280px;
}

#so{
  margin-top: 150px;
}

.objTxt{
  text-align: center;
  font-family: "Black Han Sans";
}

#topElevator{
  position: sticky;
  top: 5px;
}

#logo{
  height: 25px;
  width: 78px;
}

#balanceDiv{
  width: 100%;
  display: flex;
  justify-content: start;
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
  margin-right: 30px;
}

#steroidsPics{
  width: 100%;
  height: auto;
  margin-right: 50px
}

#footerDiv{
  width: 100%;
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
  height: auto;
  width: 100%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

#diag{
  height: 307px;
  width: 383px;
}

#kidneyBtn{
  position: absolute;
  margin-top: 305px;
  margin-left: -190px;
}

#heartBtn{
  position: absolute;
  margin-top: 173px;
  margin-left: -213px;
}

#nutsBtn{
  position: absolute;
  margin-top: 387px;
  margin-left: -215px
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

.bodyActivity{
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
  margin-top: 50px;
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
  width: 100%;
}

#objectivePositionning img{
  position: absolute;
  z-index: -1;
}

#objectivePositionning{
  height: 225px;;
  width: 100%;
}

.decoration{
  margin-bottom: 75px;
  margin-top: 263px;
  width: 95%;
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
  width: 280px;
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
