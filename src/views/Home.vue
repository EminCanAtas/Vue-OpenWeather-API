<template>
  <div class="home">
    <Weather />
  </div>
</template>

<script>
// @ is an alias to /src
import Weather from "@/components/Weather";

export default {
  name: "Home",
  components: {
    Weather
  },
};
</script>

<style scoped>

</style>
