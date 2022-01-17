<template>
  <button @click="$emit('addLetter', letter)" class="keyboardKey">{{ letter }}</button>
</template>

<script>

export default {
    name: 'KeyboardKey',
    props: {
        letter: String,
    },
    emits: ['addLetter']
}
</script>

<style scoped>
    .keyboardKey {
        width: 50px;
        height: 60px;
        border: none;
        border-radius: 5px;
        margin: 3px;
        display: flex;
        justify-content: center;
        align-items: center;
        text-transform: capitalize;
        font-weight: bold;
        font-size: 20px;
        color: #121212;
        background-color: gray;
        cursor: pointer;
    }
</style>