<script setup>
import IconLocation from "../icons/IconLocation.vue";
import Button from "./Button.vue";

function log() {
  console.log("Log function call");
}
</script>

<template>
  <Button @click="log()">
    <IconLocation />
    Изменить город
  </Button>
  <input />
  <Button>Сохранить</Button>
</template>
