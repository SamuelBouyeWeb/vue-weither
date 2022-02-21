<template>
  <h1>Weather app</h1>
  <WeatherCityInput />
  <WeatherCard />
</template>

<script>
import WeatherCityInput from "./WeatherCityInput.vue";
import WeatherCard from "./WeatherCard.vue";

export default {
  components: {
    WeatherCityInput,
    WeatherCard,
  },
  data() {
    return {
      //code ...
    };
  },
};
</script>

<style></style>
