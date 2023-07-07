<script>
import AppHeader from './components/AppHeader.vue';
import { api } from './data';
import { store } from './data/store';

export default {

  components: {
    AppHeader,
  },
  data() {
    return {


    }
  }
}
</script>

<template>
  <!-- header-->
  <AppHeader />

  <!-- main-->
</template>


<style>
h3 {
  color: rgb(231, 65, 23)
}
</style>