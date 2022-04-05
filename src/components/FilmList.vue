<template>
  <div class="my-container">
    <div class="container-fluid p-5">
      <h1 class="text-center text-black">BENVENUTO SU BOOLFLIX, TROVA UN FILM O SERIE TV</h1>
      <div class="row justify-content-center">
        <div v-for="(element, index) in movies" :key="index" class="col-3  m-5">
          <Film :film="element" class="img"/>
        </div>
      </div>
      <div class="row">
        <div v-for="(element, index) in seriesTv" :key="index" class="col-3 p-5 m-5">
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
    Film,
  },
}
</script>

<style scoped>
.my-container{
  background-color: grey;
}
.img{
  width: 100%;
}
</style>