<template>
    <div id="filterBtn">
        <img :src="`src/assets/objectiveFilter1.png`" alt="" class="filter"/>
        <img :src="`src/assets/objectiveFilter2.png`" alt="" class="filter"/>
        <img :src="`src/assets/objectiveFilter3.png`" alt="" class="filter"/>
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