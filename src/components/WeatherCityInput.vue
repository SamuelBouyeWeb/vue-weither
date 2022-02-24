<template>
  <div class="weahter-city-input">
    <input
      class="rounded border-2 w-full pt-3 pb-3 pl-2 outline-none"
      type="text"
      @keyup.enter="getWeather"
      v-model="city_name"
      placeholder="Los Angeles"
    />
    <div>
      <div class="" v-if="hasError">
        <p  class="font-bold text-red-500 text-lg">
          Votre entrer est incorrect
        </p>
      </div>
      <div v-else>
        <div class="font-bold text-white text-3xl text-center pt-10" v-if="loading">Loading...</div>
        <WeatherCard v-else :info="info"/>
      </div>
      
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
          loading: true,
          hasError: false,
          city_name: '',
          api_key: '92f01e7a19c2961a79399215c8f82849',
          base_url: 'https://api.openweathermap.org/data/2.5/',
          info : {}
        };
    },
    methods: {
        async getWeather() {
           await axios.get(`${this.base_url}weather?q=${this.city_name}&units=metric&appid=${this.api_key}`)
           .then((response) => {
              let result = response.data
              console.log(result);
              this.info = result
              this.city_name = ''
              this.loading = false
              if(this.hasError) {
                this.hasError = false
              }
           }).catch((err) => {
             console.error(err);
             this.hasError = true
             this.loading = true
            })
        },
    },
    
    components: { WeatherCard }
};
</script>

<style lang="scss">
  
</style>
