<template lang="html">
  <div>
    <h1>BrewDog Beers</h1>
    <div class="main-container">
      <beers-list :beers="beers"></beers-list>
      <beer-detail :beer="selectedBeer"></beer-detail>
    </div>
  </div>
</template>

<script>
import { eventBus } from './main.js'
import BeersList from './components/BeersList.vue'
import BeerDetail from './components/BeerDetail.vue'

export default {
  data(){
    return {
      beers: [],
      favouriteBeers: [],
      selectedBeer: null
    }
  },

  components: {
    "beers-list": BeersList,
    "beer-detail": BeerDetail
  },

  mounted() {
    fetch("https://api.punkapi.com/v2/beers")
    .then(res => res.json())
    .then(beers => this.beers = beers)

    eventBus.$on("beer-selected", (beer) => this.selectedBeer = beer)
    eventBus.$on("fav-beer-selected", (beer) => {
      this.favouriteBeers.push(this.selectedBeer)
      // console.log(beer);
      // console.log(this.favouriteBeers);
    })
    // console.log(beer);
    // console.log(favouriteBeers);
  }
}
</script>

<style lang="css" scoped>

</style>
