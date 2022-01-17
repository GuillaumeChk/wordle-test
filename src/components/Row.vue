<template>
  <div class="row">
      <!-- <Tile v-for="(word, index) in word" :letter="word.charAt(index)" :key="index" /> -->

      <Tile id="0" :letter="word.charAt(0)" />
      <Tile id="1" :letter="word.charAt(1)" />
      <Tile id="2" :letter="word.charAt(2)" />
      <Tile id="3" :letter="word.charAt(3)" />
      <Tile id="4" :letter="word.charAt(4)" />
  </div>
</template>

<script>
import Tile from "./Tile.vue";

export default {
    name: 'Row',
    components: {
        Tile,
    },
    props: {
        word: String,
    },
}
</script>

<style lang="scss" scoped>
    .row {
        display: inline-flex;
    }
</style>