<script setup>
import { computed, inject } from "vue";
import { cityProvide } from "../constants";
import IconLocation from "../icons/IconLocation.vue";
import IconSun from "../icons/weather/IconSun.vue";
import IconCloud from "../icons/weather/IconCloud.vue";
import IconRain from "../icons/weather/IconRain.vue";

const { dayData } = defineProps({
  dayData: Object,
});

const city = inject(cityProvide);

const day = computed(() => {
  return new Date(dayData.date).toLocaleDateString("ru-RU", {
    weekday: "long",
  });
});
const date = computed(() => {
  return new Date(dayData.date).toLocaleDateString("ru-RU", {
    day: "numeric",
    month: "long",
    year: "numeric",
  });
});
const weatherCode = computed(() => {
  return dayData.day.condition.code;
});
</script>

<template>
  <div class="paneLeft">
    <div>
      <div class="day">
        {{ day }}
      </div>
      <div class="date">
        {{ date }}
      </div>
      <div class="city">
        <IconLocation />
        {{ city }}
      </div>
    </div>
    <div>
      <div class="wetherIcon">
        <IconSun v-if="weatherCode <= 1003" size="95" />
        <IconCloud v-if="weatherCode >= 1006 && weatherCode < 1063" size="95" />
        <IconRain v-if="weatherCode >= 1063" size="95" />
      </div>
      <div class="temp">
        {{ dayData.day.avgtemp_c }}
      </div>
      <div class="condition">
        {{ dayData.day.condition.text }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.paneLeft {
  display: flex;
  flex-direction: column;
  padding: 48px 32px;
  justify-content: space-between;
  height: 100%;
}
.day {
  font-size: 37px;
  font-weight: 700;
  text-transform: capitalize;
  margin-bottom: 16px;
}
.date {
  font-size: 22px;
  font-weight: 500;
  margin-bottom: 10px;
}
.wetherIcon {
  margin: 25px;
}
.city {
  display: flex;
  gap: 8px;
  align-items: center;
}
.temp {
  font-size: 50px;
  font-weight: 700;
  margin-bottom: 9px;
}
.condition {
  font-size: 30px;
  font-weight: 700;
}
</style>
