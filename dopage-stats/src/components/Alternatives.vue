<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';

const alternatives=[
    "banane.png", "ginseng.png", "legumes.png", "oeuf.png", "poisson.png", "poulet.png", "riz.png"
]
</script>

<template>
    <div id="alternativeContainer">
        <div id="allIsNotLostDiv">
            <p class="but">MAIS</p>
            <p id="lost" class="but" >TOUT N'EST PAS PERDU</p>
            <br>
            <br>
            <p id="end">Il y a des issues et des solutions</p>
            
        </div>
        <div id="rect">
            <img src="../../public/assets/rectangle.png" alt="" id="rectImg">
        </div>
        <div id="gifs">
            <div>
                <img src="/assets/alternativesGifs/gifs1.gif" alt="" class="gifs">
                <p>Pense à bien t’hydrater</p>
            </div>
            <div>
                <img src="/assets/alternativesGifs/gifs2.gif" alt="" class="gifs">
                <p>Habitue toi à une alimentation saine et variée</p>
            </div>
            <div>
                <img src="/assets/alternativesGifs/gifs3.gif" alt="" class="gifs">
                <p>Consulte un médecin</p>
            </div>
            <div>
                <img src="/assets/alternativesGifs/gifs4.gif" alt="" class="gifs">
                <p>Pratique une activité sportive régulière</p>
            </div>
        </div>
        <div id="alternativeImages">
            <swiper
            :slides-per-view="1.5"
            :space-between="30"
            :centered-slides="true"
            :initial-slide= "1"
            >
            <SwiperSlide v-for="photo in alternatives"> 
                <img :src="`/assets/alternatives/${photo}`" alt="" class="slideImgs"/>
            </SwiperSlide>
            </swiper>
        </div>
        <div id="helpPhrases">
            <p>Tu as des problèmes avec le dopage ?</p>
            <br>
            <p>Connais quelqu’un de concerné ?</p>
            <br>
            <p>Ou tu veux juste te renseigner ?</p>
        </div>
        <div id="helpLinks">
            <div class="helpTitle">
                <img src="/assets/icons/phone.png" alt="" class="icon">
                <div id="helpTxt">
                    <h2>01 40 62 76 78</h2>
                    <br>
                    <p class="des">Service médical de l’Agence Française de Lutte contre le Dopage (AFLD)</p>
                </div>
            </div>
            <br>
            <br>
            <br>
            <div class="helpTitle">
                <img src="/assets/icons/world.png" alt="" class="icon">
                <div id="helpTxt">
                    <a href="https://www.wada-ama.org/fr">https://www.wada-ama.org/fr</a>
                    <br>
                    <p class="des">Agence Mondiale Anti dopage (AMA)</p>
                </div>
            </div>
            <br>
        </div>
    </div>
</template>

<style>

@font-face {
  font-family: "InterLight";
  src:
    url("@/assets/Baloo_2,Inter/Inter/static/Inter_18pt-Light.ttf");
}

@font-face {
  font-family: "Black Han Sans";
  src:
    url("@/assets/BlackHanSans-Regular.ttf");
}

.but{
    font-family: "Black Han Sans";
}

.des{
    font-family: "InterLight";
}

#gifs p{
    text-align: center;
}

#gifs div{
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 155px;
}

.gifs{
    height: 140px;
    width: 155px;
}

#gifs{
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    padding: 44px;
}

#allIsNotLostDiv{
    width: 100%;
    padding-left: 25px;
    padding-right: 25px;
}

#lost{
    color: #10EC00;
}

#rectImg{
    width: 100%;
    height: auto;
}

#rect{
    width: 100%;
    display: flex;
    justify-content: center;
    padding: 40px;
    padding-top: 0px;
}

.icon{
    height: 36px;
    margin-right: 20px;
}

.helpTitle{
    display: flex;
}

#helpPhrases{
    font-size: 16px;
    margin-bottom: 50px;
}

#helpLinks{
    width: 100%;
    margin-bottom: 50px;
    padding-left: 70px;
    padding-right: 49px;
}
#end{
    text-align: end;
    margin-bottom: 30px;
}

#alternativeContainer{
    display: flex;
    flex-direction: column;
    align-items: center;
    height: auto;
}

#alternativeImages{
  /* margin-top: 240%; */
  margin-top: 50px;
  height: 432px;
  width: 384px;
}

.slideImgs{
    height: 275px;
    width: 250px;
}
</style>