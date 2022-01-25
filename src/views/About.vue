<template>
  <div v-if="result" class="about">

    <h1>The weather </h1>
    <img :src="'http://openweathermap.org/img/w/'+result.weather[0].icon+'.png' " alt="iconweather">
    <p>{{result.weather[0].description}}</p>
    <p>Name: {{ result.name }}</p>
    <p>temp: {{ result.main.temp }}</p>
    <p>degrees: {{ result.wind.deg }}</p>
    <p>visibility: {{result.visibility}} </p>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data: () => ({
    result: null,
  }),
  created() {
    axios.get("api.openweathermap.org/data/2.5/weather?q=playa%20del%20carmen&appid={d9d025affffb89c75f8653c84b044b40}").then((result) => {
      //console.log(result.data);
      this.result + result.data;
    });
  },
}
</script>