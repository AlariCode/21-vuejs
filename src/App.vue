<script setup>
import { reactive, ref } from "vue";
import CitySelect from "./components/CitySelect.vue";
import Stat from "./components/Stat.vue";

let savedCity = ref("Moscow");
let data = reactive({
  label: "Влажность",
  stat: "90%",
});

const counter = reactive({
  count: ref(0),
});
counter.count++;
console.log(counter.count);

// Нет unwrap
const map = reactive(new Map([["count", ref(0)]]));
map.get("count").value;

// Нет unwrap
const arr = reactive([ref(0)]);
arr[0].value;

const obj = { id: ref(1) };
const id = obj.id;

function getCity(city) {
  savedCity.value = city;
  data.stat = "20%";
}
</script>

<template>
  <main class="main">
    {{ savedCity }}
    {{ id + 1 }}
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
