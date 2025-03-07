<script setup>
import { ref } from "vue";
import CitySelect from "./components/CitySelect.vue";
import Stat from "./components/Stat.vue";

let savedCity = ref("Moscow");
let data = ref({
  label: "Влажность",
  stat: "90%",
});
let arr = ref([1]);
let map = ref(new Map([["1", 1]]));

function getCity(city) {
  savedCity.value = city;
  data.value.stat = "20%";
  arr.value.push(2);
  map.value.set("2", 2);
}
</script>

<template>
  <main class="main">
    {{ savedCity }}
    {{ arr }}
    {{ map }}
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
