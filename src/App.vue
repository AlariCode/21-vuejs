<script setup>
import { computed, ref } from "vue";
import CitySelect from "./components/CitySelect.vue";
import Stat from "./components/Stat.vue";

let savedCity = ref("Moscow");
let data = ref({
  humidity: 90,
});

const arr = ref(["Anton", "Vasia", "Marina"]);
const obj = ref({
  name: "Anton",
  age: 18,
});

const dataModified = computed(() => {
  return {
    label: "Влажность",
    stat: data.value.humidity + "%",
  };
});

async function getCity(city) {
  savedCity.value = city;
  data.value.humidity = 20;
}
</script>

<template>
  <main class="main">
    <ul>
      <li v-for="(item, index) in arr" :key="item">{{ index }}: {{ item }}</li>
    </ul>
    <ul>
      <li v-for="(value, key, index) in obj" :key="key">
        {{ index }}: {{ value }}, {{ key }}
      </li>
    </ul>
    <div id="city">{{ savedCity }}</div>
    <Stat v-bind="dataModified" />
    <Stat label="Осадки" stat="0%" />
    <CitySelect @select-city="getCity" />
  </main>
</template>

<style scoped>
.main {
  background: var(--color-bg-main);
  padding: 60px 50px;
  border-radius: 25px;
}
</style>
