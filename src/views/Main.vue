<template>
    <div>
        <Header />
        <router-view />
        <Footer />
    </div>
</template>

<script>
import Header from '../components/Header.vue';
import Footer from '../components/Footer.vue';

export default {
    name: "MainPage",
    components: {
        Header,
        Footer,
    },
};
</script>

<style>
/* Estilos globales */
body {
margin: 0;
font-family: Arial, sans-serif;
}
</style>