<script setup>
import { onMounted } from 'vue';
</script>

<template>
    <div id="positionDiv">
        <div id="testDiv">
            <div id="img" @click="handleClick">
                <img src="@/assets/sideEffects/hand.png" alt="">
            </div>
            <div id="text" @click="handleClick">
                <p>Au début, je me sentais très bien, je dormais très bien...
                    mais les effets secondaires, comme la rétention d'eau, étaient horribles.</p>
            </div>
        </div>
    </div>
</template>

<style>
#greenPoints{
    opacity: 0.12;
    position: absolute;
}

#positionDiv{
    display: flex;
    justify-content: center;
    width: 100%;
    margin-bottom: 20px;
}

#testDiv{
    width: 240px;
    height: 215px;
}

@font-face {
  font-family: "InterLight";
  src:
    url("@/assets/Baloo_2,Inter/Inter/static/Inter_18pt-Light.ttf");
}

#text{
    position: absolute;
    background-color: #557BBD;
    padding: 20px;
    color: white;
    width: 240px;
    height: 157px;
    font-family: "InterLight";
    margin-top: 30px;
    margin-left: 85px;
}

#img{
    position: absolute;
    width: 172px;
    height: 209px;
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