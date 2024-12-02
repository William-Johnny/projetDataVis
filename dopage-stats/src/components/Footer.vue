<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
    <footer>
        <div>
            <img src="../../public//assets/webLogo.png" alt="">
            <img src="../../public//assets/rest.png" alt="">
        </div>
        <div id="titles"><p>Contact</p><p>Suivez-nous</p></div>
        <div>
            <RouterLink to="/">crédits</RouterLink>
            <RouterLink to="/">mentions légales</RouterLink>
            <RouterLink to="/">CGV</RouterLink>
            <RouterLink to="/">règlement intérieur</RouterLink>
            <RouterLink to="/confidentiality">politique de confidentialité & rgpd</RouterLink>
        </div>
        <p>Tous droits réservés - InPulse </p>
    </footer>
    <RouterView />
</template>

<style>
footer{
    /* position: absolute; */
    /* top: 171%; */
    background-image: url("/assets/bgGreenPoints.png");
    padding: 20px;
}

#titles{
    display: flex;
    justify-content: space-between;
}
</style>