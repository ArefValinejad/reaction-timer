<template>
  <h1>Reaction Timer</h1>
  <button class="btn" @click="start" :disabled="isPlaying">Play</button>

  <ButtonBox v-if="isPlaying" />
</template>

<script>
import ButtonBox from "./components/ButtonBox.vue";

export default {
  name: "App",
  components: { ButtonBox },
  data() {
    return {
      delay: null,
      isPlaying: false,
      showResult: false,
      score: null,
      rank: null,
    };
  },
  methods: {
    start() {
      // this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResult = true;
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
  color: #444;
  margin-top: 60px;
}
.btn {
  background: #bb03df;
  color: aliceblue;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
.btn[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
