<template>
  <div>
    <h1>WORDLE</h1>
    <GameGrid :grid="grid" />
    <Keyboard @addLetter="addLetter" @validate="validate" @clear="clear" />
    <div class="result" v-if="showResult">
      <p>
        {{ result }}
      </p>
      <button class="closeBtn" @click="this.showResult = false">X</button>
    </div>
  </div>
</template>

<script>
import GameGrid from "./components/GameGrid.vue";
import Keyboard from "./components/Keyboard.vue";

export default {
  name: "App",
  components: {
    GameGrid,
    Keyboard,
  },
  data() {
    return {
      grid: ["", "", "", "", "", ""],
      currentRow: 0,
      word: "",
      wordsList: ["loupe", "aigle", "chien", "boite", "flute"],
      result: "GAGNÉ",
      showResult: false,
    };
  },
  methods: {
    addLetter(letter) {
      if (this.grid[this.currentRow].length < 5) {
        this.grid[this.currentRow] += letter;
      }
    },
    getRandomInt(max) {
      return Math.floor(Math.random() * max);
    },
    validate() {
      const word = this.grid[this.currentRow];
      if (word === this.word && this.wordsList.includes(word)) {
        this.result = "GAGNÉ";
        this.showResult = true;
        console.log("GAGNÉ");
      } else if (this.wordsList.includes(word)) {
        console.log("Incorrect");
        this.currentRow++;
        if (this.currentRow == 6) {
          console.log("perdu");
          this.result = "PERDU";
          this.showResult = true;
        }
      } else {
        console.log("mot entré : " + word);
        console.log("mot à trouver : " + this.word);
        this.result = "Ce mot n'est pas dans la liste.";
        this.showResult = true;
      }
    },
    clear() {
      if (this.grid[this.currentRow].length > 0) {
        this.grid[this.currentRow] = this.grid[this.currentRow].slice(0, -1);
      }
    },
  },
  mounted() {
    this.word = this.wordsList[this.getRandomInt(this.wordsList.length - 1)];
  },
};
</script>

<style lang="scss">
html {
  background-color: #121212;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #121212;
}
h1 {
  color: lightgray;
  font-size: 2.5em;
  letter-spacing: 2px;
}
.result {
  position: absolute;
  top: 10%;
  left: 10%;
  height: 80%;
  width: 80%;
  font-size: 30px;
  border-radius: 40px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  background-color: #212121;
  color: whitesmoke;
}
.closeBtn {
  color: gray;
  border: none;
  background-color: #121212;
  font-size: 1em;
  padding: 10px;
  border-radius: 10px;
}
</style>
