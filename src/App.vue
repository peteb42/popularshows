<template>
  <div id="app">
    <!-- Both tags represent the components with the contained code(Header, Card) -->
    <Header/>
    <Card/>
  </div>
</template>

<script>
// import both of the vue components you created into App.vue
import Header from './components/Header.vue'
import Card from './components/Card.vue'
//import axios from 'axios'

export default {
  name: 'App',
  //These are the components you created to include in your website
  components: {
    Header,
    Card
  },
  /*
  data() {
    return {
      results: ''
    }
  },

  mounted() {
    axios.get("https://api.themoviedb.org/3/tv/popular?api_key=7a382377ded02d04b294930106237183&language=en-US&page=1")
    .then((response) => {
      this.results = response.data.results;
    })
  }
  */
}
</script>

<style>
* {
  margin:0;
  padding:0;
}
#app {
  font-family:Arial;
  overflow-x:hidden;
}
</style>
