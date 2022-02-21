<template>
  <div class="weahter-city-input">
      <input type="text" @keyup.enter="sendCity" v-model="weather" placeholder="Los Angeles" />
  </div>
</template>

<script>
export default {
    props : ['weather', 'getweather'],        
    data(){
        return {
            // city : ''
        }
    },
  watch: {
    weather(newWeather){
      console.log(newWeather);
      if(newWeather){
        this.cityName = newWeather
        this.getweather()
      } 
    }
  },
    methods : {
        sendCity(){
            console.log(this.weather);
            this.$emit('getCity', this.city)
        }
    }
}
</script>

<style>

</style>