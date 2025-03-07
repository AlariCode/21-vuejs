<script setup>
import CitySelect from "./components/CitySelect.vue";
import Stat from "./components/Stat.vue";
const data = {
  label: "Влажность",
  stat: "90%",
};
let savedCity = "Moscow";

function getCity(city) {
  console.log(city);
  savedCity = city;
}
</script>

<template>
  <main class="main">
    {{ savedCity }}
    <Stat v-bind="data" />
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
