<script setup>
import Button from "./components/Button.vue";
import IconLocation from "./icons/IconLocation.vue";
import Stat from "./components/Stat.vue";
const data = {
  label: "Влажность",
  stat: "90%",
};
</script>

<template>
  <main class="main">
    <Stat v-bind="data" />
    <Stat label="Осадки" stat="0%" />
    <Button>
      <IconLocation />
      Сохранить
    </Button>
  </main>
</template>

<style scoped>
.main {
  background: var(--color-bg-main);
  padding: 60px 50px;
  border-radius: 25px;
}
</style>
