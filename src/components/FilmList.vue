<template>
  <div>
    <div class="container-fluid p-5">
      <div class="row">
        <div v-for="(element, index) in movies" :key="index" class="col-2 p-5 m-5">
          <Film :film="element"/>
        </div>
      </div>
      <div class="row">
        <div v-for="(element, index) in seriesTv" :key="index" class="col-2 p-5 m-5">
          <Film :film="element"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Film from './Film.vue'
export default {
  name : "FilmList",
  props: {
    'movies' : Array,
    'seriesTv' : Array
  },
  components: {
    Film
  },
}
</script>

<style>

</style>