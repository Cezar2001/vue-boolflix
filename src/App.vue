<template>
  <div id="app">
    <nav-bar @search="chooseFilm" />
    <main-container :filmList="filmList" />
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
    }
  },
  methods: {
    chooseFilm(keyword) {
      let url = "https://api.themoviedb.org/3/search/movie?query=";
      let apiId = "&api_key=f655c752493edcdf5f88d9b75b5667fd";
      axios.get(url + keyword + apiId).then((response) => {
        this.filmList = response.data.results;
      })
    }
  }
}
</script>

<style lang="scss">
@import './style/main.scss' 
</style>
