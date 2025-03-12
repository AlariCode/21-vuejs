<script setup>
import { ref } from "vue";
import IconLocation from "../icons/IconLocation.vue";
import Button from "./Button.vue";

const emit = defineEmits({
  selectCity(payload) {
    return payload;
  },
});

let isEdited = ref(false);

function select() {
  isEdited.value = false;
  emit("selectCity", "London");
}

function edit() {
  isEdited.value = true;
}
</script>

<template>
  {{ isEdited }}
  <Button @click="edit()">
    <IconLocation />
    Изменить город
  </Button>
  <input />
  <Button @click="select()">Сохранить</Button>
</template>
