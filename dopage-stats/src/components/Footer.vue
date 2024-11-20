<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
    <footer>
        <div>
            <img src="@/assets/webLogo.png" alt="">
            <img src="@/assets/rest.png" alt="">
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
    background-color: #FEFFF2;
    padding: 20px;
}

#titles{
    display: flex;
    justify-content: space-between;
    width: 100%;
}
</style>