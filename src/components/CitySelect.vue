<script setup>
import { ref } from "vue";
import IconLocation from "../icons/IconLocation.vue";
import Button from "./Button.vue";
import Input from "./Input.vue";

const emit = defineEmits({
  selectCity(payload) {
    return payload;
  },
});

let city = ref("Moscow");
let isEdited = ref(false);

function select() {
  isEdited.value = false;
  emit("selectCity", "London");
}

function edit() {
  isEdited.value = true;
}

function updateCity(newCity) {
  city.value = newCity;
}
</script>

<template>
  <div class="city-select">
    {{ city }}
    <div v-show="isEdited" class="city-input">
      <Input
        placeholder="Введите город"
        :value="city"
        @update:value="updateCity"
      />
      <Button @click="select()">Сохранить</Button>
    </div>
    <Button v-show="!isEdited" @click="edit()">
      <IconLocation />
      Изменить город
    </Button>
  </div>
</template>

<style scoped>
.city-input {
  display: flex;
  gap: 12px;
}
.city-select {
  width: 420px;
}
</style>
