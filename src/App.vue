<template>
  <div id="app">
    <Header @searchChar="newSearch"/>
    <FilmList :searchString="searchString"/>
  </div>
</template>

<script>
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
      searchString : ""
    }
  },
  methods: {
    newSearch(stringToSearch){
      console.warn(stringToSearch);
      this.searchString = stringToSearch
    }
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
