<script setup>
import { ref } from 'vue';

const aValue = ref(0);
const bValue = ref(0);
const degree = ref(0);
const result = ref(0);

function cosineLaw() {
  const angleInRadians = degree.value * (Math.PI / 180);
  result.value = Math.sqrt(
    aValue.value * aValue.value +
    bValue.value * bValue.value -
    2 * bValue.value * aValue.value * Math.cos(angleInRadians)
  );
}
</script>

<template>
  <div class="cosinelaw">
    <h3>Cosine Calculation</h3>
    <input v-model="aValue" type="number" placeholder="Side A" />
    <input v-model="bValue" type="number" placeholder="Side B" />
    <input v-model="degree" type="number" placeholder="Angle (°)" />
    <input :value="result" readonly placeholder="Result"/>
    <button @click="cosineLaw">Calculate</button>
  </div>
</template>


<style scoped>
.cosinelaw{
    background-color: #ffffff;
    border: 1px solid #ddd;
    border-radius: 12px;
    padding: 20px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s, box-shadow 0.2s;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.cosinelaw:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

button {
    background-color: #007BFF;
    color: #ffffff;
    border: none;
    border-radius: 8px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #0056b3;
}

h3 {
    margin-bottom: 15px;
    color: #333;
    text-align: center;
}

input[readonly] {
    background-color: #e9ecef;
    color: #333;
    border: none;
}

input[type="number"],
button,
input[readonly] {
    width: 100%;
    padding: 10px;
    margin-bottom: 15px;
    border: 1px solid #ccc;
    border-radius: 8px;
    font-size: 14px;
    box-sizing: border-box;
}
</style>
