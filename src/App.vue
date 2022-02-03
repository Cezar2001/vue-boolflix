<template>
  <div id="app">
    <nav-bar @search="chooseFilm" />
    <main-container />
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue';
import MainContainer from './components/MainContainer.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    NavBar,
    MainContainer
  },
  data() {
    return{
      filmList:[],
      filmListFiltered:[],
    }
  },
  methods: {
    chooseFilm() {
      let url = "https://api.themoviedb.org/3/search/movie?query=";
      let keyword = "@search"
      let apiId = "&api_key=f655c752493edcdf5f88d9b75b5667fd"
        const link = axios.get(url + keyword + apiId).then((results) => {
        this.filmList = results.data  
        this.filmListFiltered = results.data  
      })
      this.filmList.push(link);
      // return link.title
      console.log(link.title)
    },
  //   stampFilm() {
  //     this.filmListFiltered = this.filmList.
  //   }
  }
}
</script>

<style lang="scss">
@import './style/main.scss' 
</style>
