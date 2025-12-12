<template>
  <div class="app">
    <!-- Свечения как фон -->
    <div class="light light-1"></div>
    <div class="light light-2"></div>
    <div class="light light-3"></div>
    <div class="light light-4"></div>
    <div class="light light-5"></div>
    
    <!-- Основной контент -->
    <Header />
    <Main/>
    <Footer/>
  </div>
</template>

<script setup lang="ts">
  import Header from './components/layout/Header.vue';
  import Main from './components/layout/Main.vue';
  import Footer from './components/layout/Footer.vue';
</script>

<style scoped>
.app {
  position: relative;
  overflow: hidden;
}

.light {
  position: absolute;
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
  pointer-events: none;
  z-index: -1;
  animation: light-anim 7s ease infinite;
}

.light-1 {
  background-image: url(./assets/images/lights/1.png);
  width: 723px;
  height: 834px;
  top: 563px;
  left: -120px;
}

.light-2 {
  background-image: url(./assets/images/lights/2.png);
  width: 964px;
  height: 985px;
  top: 687px;
  right: -290px;
}

.light-3 {
  background-image: url(./assets/images/lights/3.png);
  width: 732px;
  height: 834px;
  top: 1432px;
  left: -150px;
}

.light-4 {
  background-image: url(./assets/images/lights/4.png);
  width: 964px;
  height: 985px;
  top: 1897px;
  right: -250px;
}

.light-5 {
  background-image: url(./assets/images/lights/5.png);
  width: 732px;
  height: 834px;
  bottom: -30px;
  left: 0;
}


@keyframes light-anim {
  0%, 100% {scale: 1; transform: translate(0, 10px);}
  50% {scale: 1.3; transform: translate(0, -50px);}
}

</style>