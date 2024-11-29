<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination } from 'swiper/modules'; // Import the Pagination module
import 'swiper/css';
import 'swiper/css/pagination';

const originalCelebsPhotosRecto = [
  ["carteAshley1.png", 0],
  ["carteBlackWidow1.png", 1],
  ["carteRonnie1.png", 2],
  ["carteWolverine1.png", 3],
];

const celebsPhotosVerso = [
  ["carteRonnie1.png", 0],
  ["carteRonnie1.png", 1],
  ["carteRonnie1.png", 2],
  ["carteWolverine1.png", 3],
];

let celebsPhotosRecto = [...originalCelebsPhotosRecto];
let isShowingVerso = false;

function togglePhotos(id) {
  celebsPhotosRecto[id] = isShowingVerso
    ? [...originalCelebsPhotosRecto[id]]
    : [...celebsPhotosVerso[id]];
  isShowingVerso = !isShowingVerso;
}
</script>

<template>
    <div id="celebs">
        <swiper
            pagination
            :slides-per-view="1.6"
            :space-between="40"
            :centered-slides="true"
            :initial-slide="1"
            :modules="[Pagination]"
        >
            <SwiperSlide v-for="photo in celebsPhotosRecto" :key="photo[1]">
            <img
                :src="`/assets/celebs/${photo[0]}`"
                alt=""
                class="celebImg"
                :id="photo[1]"
                @click="togglePhotos(photo[1])"
            />
            </SwiperSlide>
        </swiper>
    </div>
</template>

<style>
.celebImg{
  width: 225px;
  height: 350px;
}
#celebs{
  /* margin-top: 240%; */
  height: 432px;
  width: 384px;
}
.swiper-pagination{
    height: 20px;
    width: 100%;
    position: relative;
    top: 10px;
}
</style>
  