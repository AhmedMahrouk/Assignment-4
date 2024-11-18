<script setup>
import CosineLaw from './components/CosineLaw.vue';
import GregoryLeibnizPi from './components/GregoryLeibnizPi.vue'
import AsymptoteFinder from './components/AsymptoteFinder.vue'
</script>

<template>
<body>
  <div class="calculaterbox">
    <CosineLaw />
    <AsymptoteFinder/>
    <GregoryLeibnizPi/>
  </div>
</body>
</template>

<style scoped>
.calculaterbox {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 20px;
    max-width: 700px;
    width: 100%;
}
body {
    background-color: #f7f9fc;
    font-family: 'Arial', sans-serif;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    padding: 40px;
    margin: 0;
}
</style>
