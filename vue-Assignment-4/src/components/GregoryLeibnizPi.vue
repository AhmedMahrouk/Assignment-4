<script setup>
import { ref } from 'vue';

const aValue = ref(0);
const result = ref('');

function piApproximation() {

    let piApproximation = 0;
    for (let i = 0; i < aValue.value; i++) {
        piApproximation += (Math.pow(-1, i)) / (2 * i + 1);
    }
    piApproximation *= 4;
    result.value = `The value of π approximation is ${piApproximation}.`;

}
</script>

<template>
    <div class="piapproximation">
        <h3>Pi Approximation</h3>
        <input v-model="aValue" type="number" placeholder="Numerator Degree (m)" />
        <input :value="result" readonly placeholder="Result" />
        <button @click="piApproximation">Calculate</button>
    </div>
</template>

<style scoped>
.piapproximation{
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

.piapproximation:hover {
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