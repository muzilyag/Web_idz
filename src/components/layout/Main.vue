<template>
    <main class="main">
        <About/>
        <TextBlock/>
        <OurTeam/>
        <OurAdvisior/>
        <ContactUs/>
        <Footer/>
    </main>
</template>

<script setup lang="ts">
import About from '../sections/About.vue';
import TextBlock from '../sections/TextBlock.vue';
import OurTeam from '../sections/OurTeam.vue';
import OurAdvisior from '../sections/OurAdvisior.vue';
import ContactUs from '../sections/ContactUs.vue';
import Footer from './Footer.vue';
</script>