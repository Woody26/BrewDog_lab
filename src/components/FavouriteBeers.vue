<template lang="html">
  <div id="favouritesList" v-if="favouriteBeers">
    <h2>Favourite Beers</h2>
      <ul>
        <list-item v-for="(favouriteBeer, index) in favouriteBeers" :beer="favouriteBeer" :key="index"></list-item>
      </ul>
  </div>
</template>

<script>
import ListItem from './ListItem.vue'
export default {
  name: 'beers-list',
  props: ['favouriteBeers'],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
