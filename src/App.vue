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
      titleFilter: ''


    }
  },
  methods: {
    setTitleFilter(term) {
      this.titleFilter = term;
    },
    searchMovie() {
      console.log(this.titleFilter);
    }
  }
}


</script>

<template>
  <!-- header-->
  <AppHeader @term-change="setTitleFilter" @form-submit="searchMovie" />

  <!-- main-->
</template>


<style>
h3 {
  color: rgb(231, 65, 23)
}
</style>