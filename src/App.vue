<script setup>
import Button from "./components/Button.vue";
const id = "blue";
</script>

<template>
  <header :class="`color-${id}`">Лого</header>
  <Button />
  <main :id>Контент</main>
</template>

<style scoped></style>
