<template lang="html">
  <div v-if="beer" id="beerDetail">
    <h2>{{ beer.name }}</h2>
    <div>
      <p>Tagline: {{beer.tagline}}</p>
      <p>Descirption: {{beer.description}}</p>
      <img :src="beer.image_url" :alt="beer.name">
    </div>
  </div>
</template>

<script>
export default {
  name: "beer-detail",
  props: ["beer"]
}
</script>

<style lang="css" scoped>
img {
  height: 100px;
}
</style>
