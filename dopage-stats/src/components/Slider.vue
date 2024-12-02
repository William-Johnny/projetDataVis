<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination } from 'swiper/modules'; // Import the Pagination module
import 'swiper/css';
import 'swiper/css/pagination';
</script>



<style>
.sex {
    background-color: #2962FF;
    color: white;
    font-family: 'Arial', sans-serif;
    font-size: 18px;
    padding: 10px 20px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
}

.sex:hover {
    background-color: #174EA6; /* Slightly darker blue on hover */
}

#example{
  text-align: center;
  width: 68%;
}

#sexBtn{
  margin-top: 20px;
  margin-bottom: 50px;
  display: flex;
  justify-content: space-evenly;
  width: 90%;
}

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
  <h2 id="example">Par exemple, si tu pouvais choisir ton physique de rêve, quel serait ton choix ?</h2>
    <div id="sexBtn">
      <button class="sex" @click="toggleSex(1)" >Corps masculins</button>
      <button class="sex" @click="toggleSex(0)" >Corps féminins</button>
    </div>
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
      // Arrays for male and female categories
      originalCelebsPhotosRecto: [
      ["carteAshley1.png", 0],
    ["carteBlackWidow1.png", 1],
    ["carteRonnie1.png", 2],
    ["carteWolverine1.png", 3],
      ],
      originalcelebsPhotosVerso: [
      ["gV.png", 0],
      ["johansonV.png", 1],
      ["colemanV.png", 2],
      ["wolverineV.png", 3],
      ],
      
      malePhotosRecto: [
        ["carteRonnie1.png", 0],
        ["carteWolverine1.png", 1],
      ],
      femalePhotosRecto: [
        ["carteAshley1.png", 0],
        ["carteBlackWidow1.png", 1],
      ],
      malePhotosVerso: [
        ["colemanV.png", 0],
        ["wolverineV.png", 1],
      ],
      femalePhotosVerso: [
        ["gV.png", 0],
        ["johansonV.png", 1],
      ],
      // Current state
      celebsPhotosRecto: [],
      celebsPhotosVerso: [],
      isShowingVerso: false, // Toggle for verso/recto view
    };
  },
  mounted() {
    // Default to female category on mount
    this.toggleSex(2);
  },
  methods: {
    toggleSex(sex) {
      // Update the current arrays based on the selected category
      if (sex === 1) {
        this.celebsPhotosRecto = [...this.malePhotosRecto];
        this.celebsPhotosVerso = [...this.malePhotosVerso];
        
      } else if (sex === 0){
        this.celebsPhotosRecto = [...this.femalePhotosRecto];
        this.celebsPhotosVerso = [...this.femalePhotosVerso];
        
      }else if (sex === 2){
        this.celebsPhotosRecto = [...this.originalCelebsPhotosRecto];
        this.celebsPhotosVerso = [...this.originalcelebsPhotosVerso];
        
      }
      // Reset the verso state to recto
      this.isShowingVerso = false;
    },
    togglePhotos(id) {
      // Toggle the clicked photo between recto and verso
      
      this.celebsPhotosRecto[id] = this.isShowingVerso
                ? [...this.originalCelebsPhotosRecto[id]]
                : [...this.celebsPhotosVerso[id]];
      this.isShowingVerso = !this.isShowingVerso;
    },
  },
};
</script>
