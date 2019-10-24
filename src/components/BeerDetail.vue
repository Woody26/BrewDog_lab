<template lang="html">
  <div v-if="beer" id="beerDetail">
    <h2>{{ beer.name }}</h2>
    <div>
      <p>Tagline: {{beer.tagline}}</p>
      <p>Descirption: {{beer.description}}</p>
      <img :src="beer.image_url" :alt="beer.name">
      <button v-on:click="handleClick" type="button" name="Favourite">Add to favourites</button>
    </div>
  </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: "beer-detail",
  props: ["beer"],
  methods: {
    handleClick(){
      eventBus.$emit('fav-beer-selected', this.beer)
    }
  }
}


</script>

<style lang="css" scoped>
img {
  height: 100px;
}
</style>
