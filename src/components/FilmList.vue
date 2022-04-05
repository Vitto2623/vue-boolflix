<template>
  <div class="my-container">
    <div class="container-fluid p-5">
      <h1 class="text-center text-black animate__animated animate__zoomIn my-shadow">BENVENUTO SU BOOLFLIX, CERCA UN FILM O SERIE TV</h1>
      <!--FILM -->
      <div class="row justify-content-center">
        <div v-for="(element, index) in movies" :key="index" class="col-3 p-5">
          <Film :film="element" class="img"/>
        </div>
      </div>
      <!--SERIE TV-->
      <div class="row justify-content-center">
        <div v-for="(element, index) in seriesTv" :key="index" class="col-3 p-5">
          <SerieTv :serie="element"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import 'animate.css';
import Film from './Film.vue'
import SerieTv from './SerieTv.vue'
export default {
  name : "FilmList",
  props: {
    'movies' : Array,
    'seriesTv' : Array
  },
  components: {
    Film,
    SerieTv
  },
}
</script>

<style scoped>
.my-container{
  background-color: black;
}

.img{
  width: 100%;
}

.my-shadow{
  box-shadow: 2px 5px 120px 35px red;
  background-color: rgba(255,0,0,0.64);
  border-radius: 23px;
}
</style>