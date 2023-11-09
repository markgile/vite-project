<script setup>
import { ref } from 'vue';

const inputText = ref('hello')
const gender = ref('')

</script>
<template>
    gender
    <select v-model="gender">
        <option value="male">Male</option>
        <option value="female">Female</option>
        <option value="others">Others</option>
    </select>
    <p v-if="gender == 'male'">
    <h1>Test display</h1>
    </p>
    <p v-else>3</p>
</template>