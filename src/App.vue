// UnitConverter
<template>
    <div>
        <h1>Temperature Converter</h1>
        <two-way-converter />
     </div>
  <div class="unit-converter">
    <label for="temperature">Temperature:</label>
    <input
      v-model="temperature"
      type="number"
      id="temperature"
      placeholder="Enter temperature"
      class="temperature-input"
    />
    <select v-model="selectedUnit" class="unit-select">
      <option value="celsius">Celsius</option>
      <option value="fahrenheit">Fahrenheit</option>
    </select>

    <button @click="convert" class="convert-button">Convert</button>

    <div v-if="convertedTemperature !== null" class="result">
      Converted Temperature: {{ convertedTemperature }} {{ targetUnit }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      temperature: null,
      selectedUnit: 'celsius',
      convertedTemperature: null,
      targetUnit: '',
    };
  },
  methods: {
    convert() {
      if (this.selectedUnit === 'celsius') {
        this.convertedTemperature = (this.temperature * 9) / 5 + 32;
        this.targetUnit = 'Fahrenheit';
      } else {
        this.convertedTemperature = ((this.temperature - 32) * 5) / 9;
        this.targetUnit = 'Celsius';
      }
    },
  },
};
</script>

<style scoped>
.unit-converter {
  max-width: 300px;
  margin: auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.temperature-input {
  width: 100%;
  padding: 10px;
  margin-bottom: 10px;
}

.unit-select {
  width: 100%;
  padding: 10px;
  margin-bottom: 10px;
}

.convert-button {
  padding: 10px 20px;
  background-color: #3498db;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.convert-button:hover {
  background-color: #2980b9;
}

.result {
  margin-top: 10px;
  font-weight: bold;
}

 h1 {
    text-align: center;
}

</style>