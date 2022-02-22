<template>
  <div class="weather m-4">
    <WeatherCityInput />
  </div>
</template>

<script>
import WeatherCityInput from "./WeatherCityInput.vue";

export default {
  components: {
    WeatherCityInput,
  },
  data() {
    return {
      imgData: '../assets/img/mountain.png'
    };
  },
};
</script>

<style>
</style>
