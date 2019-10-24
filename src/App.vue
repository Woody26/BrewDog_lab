<template lang="html">
  <div>
    <h1>BrewDog Beers</h1>
    <div class="main-container">
      <beers-list :beers="beers"></beers-list>
    </div>
  </div>
</template>

<script>
import { eventBus } from './main.js'
import BeersList from './components/BeersList.vue'

export default {
  data(){
    return {
      beers: []
    }
  },

  components: {
    "beers-list": BeersList
  },

  mounted() {
    fetch("https://api.punkapi.com/v2/beers")
    .then(res => res.json())
    .then(beers => this.beers = beers)
  }
}
</script>

<style lang="css" scoped>
</style>
