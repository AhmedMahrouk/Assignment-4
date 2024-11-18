<script setup>
import { ref } from 'vue';

const aValue = ref(0);
const bValue = ref(0);
const result = ref('');

function asymptoteFinder() {
    if (aValue.value === bValue.value) {
        result.value = "The asymptote is horizontal";
    } else if (bValue.value > aValue.value) {
        result.value = "The asymptote is the x-axis";
    } else {
        let difference = aValue.value - bValue.value;
        result.value = `The asymptote difference is ${difference}.`;
    }
}
</script>

<template>
    <div class="asymptotefinder">
        <h3>Asymptote Finder</h3>
        <input v-model="aValue" type="number" placeholder="Numerator Degree (m)" />
        <input v-model="bValue" type="number" placeholder="Denominator Degree (n)" />
        <input :value="result" readonly placeholder="Result" />
        <button @click="asymptoteFinder">Calculate</button>
    </div>
</template>


<style scoped>
.asymptotefinder{
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

.asymptotefinder:hover {
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