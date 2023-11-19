<template>
    <div>
        <button @click="generateNumber">Click Me</button>
        <ul>
            <li v-for="(number, index) in numbers" :key="index">{{ number }}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                numbers: [], 
            };
        },
        methods: {
            generateNumber() {
                const newNumber = this.numbers.length + 1;
                this.numbers.push(newNumber);
            },
        },
    };
</script>