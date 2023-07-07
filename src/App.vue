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
    searchMovie() {
      axios.get(`${api.baseUri}/search/movie?api_key=${api.key}&language=${api.language}&query=${this.titleFilter}`)
        .then(res => {
          store.movies = res.data.results;
        })
    }
  }
}

</script>

<template>
  <!-- header-->
  <AppHeader @term-change="setTitleFilter" @form-submit="searchMovie" />

  <!-- main-->
  <div class="container">
    <h3>Movies</h3>
    <ul v-for="movie in store.movies">
      <li> {{ movie.title }} </li>
      <li> {{ movie.original_title }} </li>
      <li> {{ movie.original_language }} </li>
      <li> {{ movie.vote_average }} </li>
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