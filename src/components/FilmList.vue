<template>
  <div>
    <div class="container-fluid p-5">
      <div class="row">
        <div v-for="(element, index) in newSearch(searchString)" :key="index" class="col-1 p-5 m-5">
          <Film :Film="element"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Film from './Film.vue'
import axios from "axios"
export default {
  name : "FilmList",
  props: {
    'searchString' : String
  },
  components: {
    Film
  },
  data: function(){
    return{
      listaFilm : [],
    }
  },
  created: function(){
    this.getApiFilm();
  },
  methods: {
    getApiFilm(){
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=fa81f88e60a95edc8a6cc3acf18ddfaf&query=ritorno+al+futuro')
      .then((result) =>{
        this.listaFilm= result.data.results;
        console.log(this.listaFilm);
      })
      .catch((error)=>{
        console.error(error)
      })
    },
    newSearch(stringToSearch){
      console.log(stringToSearch);
      return this.listaFilm.filter(
        (element) => element.title.includes(stringToSearch)
      )
    }
  }
}
</script>

<style>

</style>