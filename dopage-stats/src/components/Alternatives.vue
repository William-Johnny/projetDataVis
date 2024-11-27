<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';

const alternatives=[
    "banane.png", "ginseng.png", "legumes.png", "oeuf.png", "poisson.png", "poulet.png", "riz.png"
]
</script>

<template>
    <div id="alternativeContainer">
        <div>
            <p>Mais</p>
            <p>tout n'est pas perdu</p>
            <p id="end">Il y a des issues et des solutions</p>
            <img src="../../public/assets/rectangle.png" alt="">
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
        <p>Tu as des problèmes avec le dopage ?</p>
        <p>Connais quelqu’un de concerné ?</p>
        <p>Ou tu veux juste te renseigner ?</p>
        <br>
        <br>
        <span>01 40 62 76 78</span>
        <p>Service médical de l’Agence Française de Lutte contre le Dopage (AFLD)</p>
        <br>
        <br>
        <p>https://www.wada-ama.org/fr</p>
        <p>Agence Mondiale Anti dopage (AMA)</p>
    </div>
</template>

<style>
#end{
    text-align: end;
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