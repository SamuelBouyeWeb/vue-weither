<template>
  <div class="weahter-city-input">
    <input
      type="text"
      @keyup.enter="getWeather"
      v-model="cityName"
      placeholder="Los Angeles"
    />
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      cityName: null,
    };
  },
  methods: {
    getWeather() {
      const apiKey = "92f01e7a19c2961a79399215c8f82849";
      let url = `https://api.openweathermap.org/data/2.5/weather?q=${this.cityName}&appid=${apiKey}`;

      axios.get(url).then((data) => {
        console.log(data.data);
      });
    },
  },
};
</script>

<style></style>
