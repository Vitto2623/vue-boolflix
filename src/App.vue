<template>
  <div id="app">
    <Header @searchChar="searchInApi"/>
    <FilmList :movies="films" :seriesTv="series"/>
  </div>
</template>

<script>
import axios from "axios";
import Header from './components/Header.vue'
import FilmList from './components/FilmList.vue'
export default {
  name : "App",
  components: {
    Header,
    FilmList,
  },
  data: function(){
    return{
      searchString : "",
      films: [],
      series: [],
    }
  },
  methods: {
      searchInApi:function(search){
        // Search in movie
        axios
          .get(`https://api.themoviedb.org/3/search/movie?api_key=d755169d575162efa23b254cbdafa103&language=it-IT&page=1&include_adult=false&query=${search}` )
            .then((response) =>{
              this.films = response.data.results;
              console.table(this.films);
            })
            .catch((error) =>{
              console.log(error)
            });
        // Search in Series
        axios.
          get(`https://api.themoviedb.org/3/search/tv?api_key=d755169d575162efa23b254cbdafa103&language=it-IT&page=1&include_adult=false&query=${search}` )
            .then((response) =>{
              this.series = response.data.results;
              console.table(this.series);
            })
            .catch((error) =>{
              console.log(error)
            });
        },
      },
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background-color: grey;
  height: 1000px;
}
</style>
