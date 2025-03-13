<script setup>
const props = defineProps(["value"]);
const emit = defineEmits(["update:value"]);
</script>

<template>
  <input
    class="input"
    :value="props.value"
    @input="emit('update:value', $event.target.value)"
  />
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
