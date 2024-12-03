<script setup>
import { onMounted } from 'vue';
import data from '../../data.json';

const props = defineProps(['bool'])

onMounted(()=>{
    const InsTab = data.temoignage_ins;
    const SteTab = data.temoignage_ste_an;
    const testDiv = document.querySelector('#testDiv');
    console.log(InsTab);
    
    if (props.bool==="bodyDisplayedIns") {
        InsTab.forEach(element => {
            testDiv.innerHTML += `
            <div>
                <div id="img" @click="handleClick">
                <img src="../../public/assets/sideEffects/hand.png" alt="">
                </div>
                <div id="text" @click="handleClick">
                    <p>${element[0]}</p>
                    <p>${element[1]}</p>
                </div>
            </div>
        `
        });
        
    }else if (props.bool==="bodyDisplayedSte") {
        SteTab.forEach(element => {
            testDiv.innerHTML += `
        <div>
            <div id="img" @click="handleClick">
            <img src="../../public/assets/sideEffects/hand.png" alt="">
            </div>
            <div id="text" @click="handleClick">
                <p>${element[0]}</p>
                <p>${element[1]}</p>
            </div>
        </div>`
        });
    }else{
        console.log("ko");
        
        return null;
    }
})

console.log(props.bool)
</script>

<template>
    <div id="positionDiv">
        <p id="doubt">Et si tu as encore des doutes,</p>
        <div id="rect">
            <img src="/assets/doubtRect.png" alt="" id="rectImg">
        </div>
        <div id="testDiv"></div>
    </div>
</template>

<style>



#greenPoints{
    opacity: 0.12;
    position: absolute;
}

#positionDiv{
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    margin-top: 50px;
    margin-bottom: 100px;
}

#testDiv{
    width: 240px;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: auto;
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
    const InsTab = data.temoignage_ins;
    const SteTab = data.temoignage_ste_an;
    const testDiv = document.querySelector('#positionDiv');
    const props = defineProps([bool])
    if (props[0]==="bodyDisplayedIns") {
        InsTab.forEach(element => {
            testDiv.innerHTML += `<p id="doubt">Et si tu as encore des doutes,</p>
    <div id="rect">
        <img src="/assets/doubtRect.png" alt="" id="rectImg">
    </div>
    <div id="testDiv">
        <div id="img" @click="handleClick">
            <img src="../../public/assets/sideEffects/hand.png" alt="">
        </div>
        <div id="text" @click="handleClick">
            <p>${element[0]}</p>
        </div>
    </div>`
        });
        
    }else if (props[0]==="bodyDisplayedSte") {
        SteTab.forEach(element => {
            testDiv.innerHTML += `<p id="doubt">Et si tu as encore des doutes,</p>
    <div id="rect">
        <img src="/assets/doubtRect.png" alt="" id="rectImg">
    </div><div id="testDiv">
        <div id="img" @click="handleClick">
            <img src="../../public/assets/sideEffects/hand.png" alt="">
        </div>
        <div id="text" @click="handleClick">
            <p>${element[1]}</p>
        </div>
    </div>`
        });
    }else{
        console.log("ko");
        
        return null;
    }
})
</script> -->