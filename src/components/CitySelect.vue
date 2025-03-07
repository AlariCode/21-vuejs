<script setup>
import IconLocation from "../icons/IconLocation.vue";
import Button from "./Button.vue";

const emit = defineEmits({
  selectCity(payload) {
    return payload;
  },
});

function select() {
  emit("selectCity", "London");
}
</script>

<template>
  <Button @click="select()">
    <IconLocation />
    Изменить город
  </Button>
  <input />
  <Button>Сохранить</Button>
</template>
