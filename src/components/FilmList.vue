<template>
  <div class="container-fluid p-5">
    <div class="row">
      <div class="col-2 my-col" v-for="(element, index) in newSearch(searchString)" :key="index">
        <Film :Film="element"/>
      </div>
    </div>
    <!--SerieTv-->
    <div class="row">
      <div class="col-2 my-col" v-for="(element, index) in newSearchSerieTv(searchString)" :key="index">
        <Film :Film="element"/>
      </div>
    </div>
  </div>
</template>

<script>
import Film from './Film.vue'
import axios from 'axios'
export default {
    name : 'FilmList',
    props: {
      'searchString': String
    },
    components: {
      Film,
      axios
    },
    data: function(){
    return{
      listaFilm : [],
      listaSerieTv : [],
    }
  },
  created: function(){
    this.getApiFilm();
    this.getApiSerieTv();
  },
  methods: {
    newSearch(stringToSearch){
      return this.listaFilm.filter(
        (element) => element.title.toLowerCase().includes(stringToSearch.toLowerCase())
      );
    },
    newSearchSerieTv(stringToSearch){
      return this.listaSerieTv.filter(
        (element) => element.name.toLowerCase().includes(stringToSearch.toLowerCase())
      );
    },
    getApiFilm(){
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=fa81f88e60a95edc8a6cc3acf18ddfaf&query=ritorno+al+futuro')
      .then((result) =>{
        this.listaFilm = result.data.response;
        console.log(this.listaFilm);
      })
      .catch((error)=>{
        console.error(error)
      })
    }
  },
}
</script>

<style lang="scss" scoped>
.my-col{
  margin: 30px;
}
</style>