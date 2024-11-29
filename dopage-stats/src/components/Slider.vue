<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination } from 'swiper/modules'; // Import the Pagination module
import 'swiper/css';
import 'swiper/css/pagination';
</script>



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
  
<template>
  <div id="celebs">

    <swiper
      pagination
      :modules="[Pagination]"
      :slides-per-view="1.6"
      :space-between="40"
      :centered-slides="true"
      :initial-slide="1"
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

<script>
export default {
  data() {
    return {
      // Initial arrays
      originalCelebsPhotosRecto: [
      ["carteAshley1.png", 0],
  ["carteBlackWidow1.png", 1],
  ["carteRonnie1.png", 2],
  ["carteWolverine1.png", 3],
      ],
      celebsPhotosVerso: [
      ["carteRonnie1.png", 0],
  ["carteRonnie1.png", 1],
  ["carteRonnie1.png", 2],
  ["carteWolverine1.png", 3],
      ],
      // Default to the first set
      celebsPhotosRecto: [],
      isShowingVerso: false, // Track the current state
    };
  },
  mounted() {
    // Initialize the default array
    this.celebsPhotosRecto = [...this.originalCelebsPhotosRecto];
  },
  methods: {
    togglePhotos(id) {
      // Toggle the array based on the state
      this.celebsPhotosRecto[id] = this.isShowingVerso
                ? [...this.originalCelebsPhotosRecto[id]]
                : [...this.celebsPhotosVerso[id]];
      this.isShowingVerso = !this.isShowingVerso; // Toggle the state
    },
  },
};
</script>
