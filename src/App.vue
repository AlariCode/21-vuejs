<script setup>
import { nextTick, reactive, ref } from "vue";
import CitySelect from "./components/CitySelect.vue";
import Stat from "./components/Stat.vue";

let savedCity = ref("Moscow");
let data = reactive({
  label: "Влажность",
  stat: "90%",
});

async function getCity(city) {
  savedCity.value = city;
  console.log(document.querySelector("#city").innerHTML);
  await nextTick();
  console.log(document.querySelector("#city").innerHTML);
  data.stat = "20%";
}
</script>

<template>
  <main class="main">
    <div id="city">{{ savedCity }}</div>
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
