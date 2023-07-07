<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import { api } from './data';
import { store } from './data/store';

export default {

  components: {
    AppHeader,
  },
  data() {
    return {
      store,
      titleFilter: ''


    }
  },
  methods: {
    setTitleFilter(term) {
      this.titleFilter = term;
    },
    searchProductions() {
      axios.get(`${api.baseUri}/search/movie?api_key=${api.key}&language=${api.language}&query=${this.titleFilter}`)
        .then(res => {
          store.movies = res.data.results;
        });
      axios.get(`${api.baseUri}/search/tv?api_key=${api.key}&language=${api.language}&query=${this.titleFilter}`)
        .then(res => {
          store.series = res.data.results;
        });
    }
  }
}

</script>

<template>
  <!-- header-->
  <AppHeader @term-change="setTitleFilter" @form-submit="searchProductions" />

  <!-- main-->
  <div class="container">
    <h3>Movies</h3>
    <ul v-for="movie in store.movies" :key="movie.id">
      <li> {{ movie.title }} </li>
      <li> {{ movie.original_title }} </li>
      <li> {{ movie.original_language }} </li>
      <li> {{ movie.vote_average }} </li>
    </ul>
    <h3>Series</h3>
    <ul v-for="serie in store.series" :key="serie.id">
      <li> {{ serie.name }} </li>
      <li> {{ serie.original_name }} </li>
      <li> {{ serie.original_language }} </li>
      <li> {{ serie.vote_average }} </li>
    </ul>
  </div>
</template>


<style>
h3 {
  color: rgb(231, 65, 23)
}

li {

  text-transform: uppercase;
  text-decoration: none;


  color: rgb(253, 252, 252);
}

.container {
  background-color: rgb(44, 42, 42);

}
</style>