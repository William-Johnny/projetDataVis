<script setup>
    function displayBody(id) {
        console.log(id);
    }
</script>

<template>
    <div id="filterBtn">
        <img :src="`/assets/objectiveFilter1.png`" alt="" class="filter" id="muscle" @click="displayBody('muscle')"/>
        <img :src="`/assets/objectiveFilter2.png`" alt="" class="filter" id="fat" @click="displayBody('fat')"/>
        <img :src="`/assets/objectiveFilter3.png`" alt="" class="filter" id="expand" @click="displayBody('expand')"/>
    </div>
</template>

<style>
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
</style>