<script setup>
import { provide, ref } from "vue";
import PaneRight from "./components/PaneRight.vue";

const API_ENDPOINT = "https://api.weatherapi.com/v1";

let data = ref();
let error = ref();
let activeIndex = ref(0);

provide("num", activeIndex);

async function getCity(city) {
  const params = new URLSearchParams({
    q: city,
    lang: "ru",
    key: "6b04fbeb8b6a48d2ba6143411252602",
    days: 3,
  });
  const res = await fetch(`${API_ENDPOINT}/forecast.json?${params.toString()}`);
  if (res.status != 200) {
    error.value = await res.json();
    data.value = null;
    return;
  }
  error.value = null;
  data.value = await res.json();
}
</script>

<template>
  <main class="main">
    <div class="left"></div>
    <div class="right">
      <PaneRight
        :data
        :error
        :active-index="activeIndex"
        @select-index="(i) => (activeIndex = i)"
        @select-city="getCity"
      />
    </div>
  </main>
</template>

<style scoped>
.main {
  display: flex;
  align-items: center;
  justify-content: center;
}
.right {
  background: var(--color-bg-main);
  padding: 60px 50px;
  border-radius: 0 25px 25px 0;
}
.left {
  width: 500px;
  height: 680px;
  border-radius: 30px;
  background-image: url("/public/bg.png");
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
