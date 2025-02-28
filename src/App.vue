<script setup>
const id = "blue";
const isAdmin = true;
</script>

<template>
  <header :class="`color-${id}`">Лого</header>
  <main :id>Контент</main>
  <div>{{ isAdmin ? "Админ" : "Не админ" }}</div>
  <footer>{{ 10 + 20 }}</footer>
</template>

<style scoped></style>
