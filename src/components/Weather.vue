<template>
  <h1>Weather app</h1>
  <WeatherCityInput @get-city="getCity" :weather="weather" :getweather="getweather" />
  <WeatherCard />
</template>

<script>
import axios from 'axios'
import WeatherCityInput from './WeatherCityInput.vue'
import WeatherCard from './WeatherCard.vue'

export default {
  components : {
    WeatherCityInput,
    WeatherCard
  },
  data(){
    return {
      weather : '',
      cityName : 'Abidjan'
    }
  },
  methods: {
    getCity(city){
      this.city = city
    },
    getweather(){
    const apiKey = '92f01e7a19c2961a79399215c8f82849'
    let url = `https://api.openweathermap.org/data/2.5/weather?q=${this.cityName}&appid=${apiKey}`

    axios
    .get(url)
    .then((data) => {
      console.log(data.data)
    })
    }
  },
  updated() {
    console.log(this.weather);
  }
}
</script>

<style>

</style>