<script setup>
import { onMounted } from 'vue';
</script>

<template>
    <div id="buttons">
        <img src="@/assets/objectiveFilter1.png" alt="" class="objective" >
        <img src="@/assets/objectiveFilter2.png" alt=""  class="objective">
        <img src="@/assets/objectiveFilter3.png" alt=""  class="objective">
    </div>
</template>

<style>
#buttons{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.objective{
    margin: 10px;
}
</style>

<!-- <script>

onMounted(()=>{
    const text = document.querySelector("#text");
    const img = document.querySelector("#img");
    text.style.zIndex = "1";
    img.style.zIndex = "0";

    text.addEventListener("mouseup", (e) => {
        console.log("ok");
        
        text.style.zIndex = "1";
        img.style.zIndex = "0";
    });

    img.addEventListener("mouseup", (e) => {
        text.style.zIndex = "0";
        img.style.zIndex = "1";
    });


})
</script> -->