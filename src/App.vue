<!-- <script setup>
const id = "blue";
</script> -->
<script>
export default {
  data() {
    return {
      id: "blue",
    };
  },
};
</script>

<template>
  <header :class="`color-${id}`">Лого</header>
  <main :id>Контент</main>
</template>

<style scoped></style>
