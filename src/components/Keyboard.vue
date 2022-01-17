<template>
  <div class="keyboard">
        <KeyboardKey 
            v-for="(letter, index) in keyboard" 
            :letter="letter" 
            :key="index" 
            @addLetter="$emit('addLetter', letter)"
        />
        <button class="validateButton" @click="$emit('validate')" >Valider</button>
        <button class="clearButton" @click="$emit('clear')" >Effacer</button>
  </div>
</template>

<script>
import KeyboardKey from './KeyboardKey.vue'

export default {
    name: 'Keyboard',
    components: {
        KeyboardKey,
    },
    data() {
        return {
        keyboard: [ 'a','z','e','r','t','y','u','i','o','p','q','s','s','d','f','g','h','j','k','l','m','w','x','c','v','b','n' ],
        }
    },
    emits: ['addLetter','validate','clear']
}
</script>

<style scoped>
    .keyboard {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        margin: 40px auto;
        max-width: 500px;
    }

    button {
        width: auto;
        height: 60px;
        border: none;
        border-radius: 5px;
        margin: 3px;
        padding: 10px;
        display: flex;
        justify-content: center;
        align-items: center;
        text-transform: capitalize;
        font-weight: bold;
        font-size: 20px;
        color: #121212;
        cursor: pointer;
    }
    .validateButton {
        background-color: forestgreen;
    }
    .clearButton {
        background-color: orange;
    }
</style>