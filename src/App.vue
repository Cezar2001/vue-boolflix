<template>
  <div id="app">
    <nav-bar @search="research" />
    <main-container 
    :filmList="filmList"
    :serisList="seriesList" 
    :popularList="popularList"
    />
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
    MainContainer,
  },
  data() {
    return{
      filmList:[],
      seriesList:[],
      popularList:[],
      api_key: 'f655c752493edcdf5f88d9b75b5667fd'
    }
  },
  mounted() {
    axios.get(`https://api.themoviedb.org/3/movie/popular?&api_key=f655c752493edcdf5f88d9b75b5667fd`).then((response) => {
      this.popularList = response.results
    })
  },
  methods: {
    research(query) {
      this.searchFilm(query)
      this.searchSeries(query)
    },
    async searchFilm(query) {
      this.filmList = await this.callApi('movie', query)
    },
    async searchSeries(query) {
      this.seriesList = await this.callApi('tv', query)
    },
    async callApi(type, query) {
      const params = {
        query: query,
        api_key: this.api_key
      }
      const results = await axios.get(`https://api.themoviedb.org/3/search/${type}`, { params })
      .then((response) => {
        return response.data.results;
      })
      return results;
    }
  }
}
</script>

<style lang="scss">
@import './style/main.scss' 
</style>
