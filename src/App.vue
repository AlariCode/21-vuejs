<script setup>
import Button from "./components/Button.vue";
import Stat from "./components/Stat.vue";
</script>

<template>
  <main class="main">
    <Stat label="Влажность" stat="90%" />
    <Stat label="Осадки" stat="0%" />
    <Button>Сохранить</Button>
  </main>
</template>

<style scoped>
.main {
  background: var(--color-bg-main);
  padding: 60px 50px;
  border-radius: 25px;
}
</style>
