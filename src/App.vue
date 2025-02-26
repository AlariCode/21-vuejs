<script setup>
const a = 10;
let b = "привет";
let c = true;
let d = {
  a: 1,
};
let e = "<a href='/'>link</a>";
</script>

<template>
  <header>{{ a }}</header>
  <main>{{ b }}</main>
  <div>{{ c }}</div>
  <div v-html="e"></div>
  <footer>{{ d.a }}</footer>
</template>

<style scoped></style>
