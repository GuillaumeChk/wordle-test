<template>
  <div class="tile">{{ letter }}</div>
</template>

<script>
export default {
    name: 'Tile',
    props: {
        letter: String,
    },
}
</script>

<style lang="scss" scoped>
    .tile {
        width: 60px;
        height: 65px;
        border: 2px solid #424242;
        margin: 3px;
        display: flex;
        justify-content: center;
        align-items: center;
        text-transform: capitalize;
        font-weight: bold;
        font-size: 30px;
        color: lightgray;
    }
</style>