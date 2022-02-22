<script setup>
import Weather from "./components/Weather.vue";
import "./index.css";

</script>

<template>
  <main>
    <Weather />
  </main>
</template>

<style>
/* @import "./assets/base.css"; */
*{
  padding: 0;
  margin: 0;
}
body{
  width: 100%;
  height: 100vh;
  background-image:  linear-gradient(
          rgba(0, 0, 0, 0.568), 
          rgba(0, 0, 0, 0.568)
        ), url('./assets/img/mountain.png'); 
  background-position: center;
  background-size: cover;
}
</style>
