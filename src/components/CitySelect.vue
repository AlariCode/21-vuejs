<script setup>
import IconLocation from "../icons/IconLocation.vue";
import Button from "./Button.vue";

const emit = defineEmits(["select-city"]);

function select() {
  emit("select-city", "London");
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
