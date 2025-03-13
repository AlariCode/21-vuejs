<script setup>
const model = defineModel();
</script>

<template>
  <input v-model="model" class="input" />
</template>

<style scoped>
.input {
  color: var(--color-primary);
  width: 260px;
  border-radius: 10px;
  height: 53px;
  border: none;
  padding: 15px 20px;
  font-size: 18px;
  background: var(--color-bg-card);
  box-shadow: 1px 2px 4px 0px var(--color-bg-main);
}
.input::placeholder {
  color: var(--color-text-placeholder);
}
</style>
