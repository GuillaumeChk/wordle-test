<template>
    <div class='gameGrid'>
        <Row v-for="(word, index) in grid" :word="word" :key="index" />
    </div>
</template>

<script>
import Row from "./Row.vue";

export default {
    name: 'GameGrid',
    components: {
        Row,
    },
    props: {
        grid: Array, // of String
    },
}
</script>

<style lang="scss" scoped>
    .gameGrid {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>