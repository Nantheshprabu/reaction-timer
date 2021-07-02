<template>
  <h1>welcome To Reaction Timer</h1>
  <button @click="start">Play</button>
  <Blocks v-if="isPlaying" :delay="delay" @end="endGame" />

  <Results v-if="showScore" :score="score" />
</template>

<script>
import Blocks from "./components/Blocks.vue";
import Results from "./components/Results.vue";

export default {
  name: "App",
  components: { Blocks, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showScore: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      this.showScore = false;
    },
    endGame(reactiontime) {
      this.score = reactiontime;
      this.showScore = true;
      this.isPlaying = false;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
