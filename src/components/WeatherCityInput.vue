<template>
  <div class="weahter-city-input">
    <input
      class="rounded border-2 w-full pt-3 pb-3 pl-2 outline-none"
      type="text"
      @keyup.enter="getWeather"
      v-model="text"
      placeholder="Los Angeles"
    />
    <div>
      <WeatherCard v-if="cityName" :info="info"/>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import WeatherCard from "./WeatherCard.vue";

export default {
  components: {
    WeatherCard
  },
    data() {
        return {
          text: '',
          cityName: null,
          info : null
        };
    },
    methods: {
        getWeather() {
          this.cityName = this.text
          if(this.city != ''){
            const apiKey = "92f01e7a19c2961a79399215c8f82849";
            let url = `https://api.openweathermap.org/data/2.5/weather?q=${this.cityName}&appid=${apiKey}&units=metric`;
            axios.get(url).then((response) => {
              this.info = response.data
              console.log(this.info);
            });
          }
        },
    },
    
    components: { WeatherCard }
};
</script>

<style lang="scss">
  
</style>
