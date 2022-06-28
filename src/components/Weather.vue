<template>
  <div>
    <div class="header">
      <div>Weather Status</div>
      <input type="text" placeholder="Pick A City..." v-on:keyup.enter="weatherFetch" v-model="city_model">
    </div>
    <div class="content" v-if="response">
      <div class="city">{{ response.name }}</div>
      <div class="temp">{{ response.main.temp }}</div>
<!--      <div class="desc">{{ response.weather[0].description }}</div>-->
      <div class="minmax">{{ response.main.temp_min }} / {{ response.main.temp_max }}</div>
      <div class="TEST">Test</div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Weather",
  data() {
    return {
      city_model: null,
      api_url: "https://api.openweathermap.org/data/2.5/weather",
      api_key: "b120674e5d172c61e3c0dab8fbd99b1b",
      response: null
    }
  },
  methods: {
    weatherFetch() {
      axios.get(this.api_url,{
        params: {
          q: this.city_model,
          appid: this.api_key,
          lang: 'tr' //@ToDo i18n must have!!
        }
      }).then(function (response) {
        return response;
      })
    }
  }
};
</script>

<style scoped>

</style>