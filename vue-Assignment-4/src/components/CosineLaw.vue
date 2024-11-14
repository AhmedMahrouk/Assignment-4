<script setup>
import { ref } from 'vue';

const aValue = ref(0);
const bValue = ref(0);
const degree = ref(0);

function cosineLaw() {

var angleInRadians = degree * (Math.PI / 180);

result.value = Math.sqrt(aValue.value * aValue.value + bValue * bValue-2*bValue*aValue*Math.cos(angleInRadians));

}
</script>

<template>
  <form @submit.prevent="cosineLaw()">
    <h3>Cosine Calculation</h3>
    <input v-model="aValue" type="number" placeholder="Side A"/>
    <input v-model="bValue" type="number" placeholder="Side B"/>
    <input v-model="degree" type="number" placeholder="Angle (°)"/>
    <input v-model="result" type="number" readonly />
    <input type="submit" value="Calculate" />
  </form>
</template>

<style scoped>
</style>
