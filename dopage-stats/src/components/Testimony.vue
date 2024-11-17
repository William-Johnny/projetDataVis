<script setup>
import data from '/data.json'
import { RouterLink, RouterView } from 'vue-router'
import { gsap } from 'gsap'
import { onMounted } from 'vue';

  
</script>

<template>
  <div id="testimony"></div>
</template>

<style scoped>
    p:hover {
        color: #10EC00;
    }
</style>

<script>
    const list = data.testimony;
    console.log(list);
    
    //list.innerHTML += `<li><a href="#">Item ${list.children.length + 1}</a></li>`;

</script>
