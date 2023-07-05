<script>
import AppHeader from './components/AppHeader.vue';
import AppHero from './components/AppHero.vue';

export default {

  components: {
    AppHeader, AppHero
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
  <AppHero />
  <ComicCard />
  <!-- main-->
  <AppMain :comic-books="comicBooks" />
</template>


<style>
h3 {
  color: rgb(231, 65, 23)
}
</style>