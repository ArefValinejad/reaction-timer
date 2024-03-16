<template>
  <div class="result">
    <p>Correct: {{ correctTimes }}</p>
    <p>Wrong: {{ wrongTimes }}</p>
    <p class="showMessage" v-if="showMessage">Game is over</p>
  </div>
  <div class="container" v-if="isPlaying">
    <div
      class="divBtn"
      :class="{ 'green-backgrond': item === randomNumber }"
      v-for="(item, index) in 9"
      :key="index"
      @click="handelClick(item)"
    ></div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      randomNumber: Math.floor(Math.random() * 9) + 1,
      correctTimes: 0,
      wrongTimes: 0,
      isPlaying: true,

      showMessage: false,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showMessage = true;
      this.isPlaying = false;
    }, 10000);
  },

  methods: {
    handelClick(id) {
      if (id === this.randomNumber) {
        this.correctTimes++;
      } else {
        this.wrongTimes++;
      }
      if (this.correctTimes + this.wrongTimes == 20) {
        console.log("done", this.isPlaying);
      }

      this.randomNumber = Math.floor(Math.random() * 9) + 1;
    },
  },
};
</script>

<style>
.container {
  /* height: 550px; */
  width: 700px;
  background-color: lightblue;
  margin-left: auto;
  margin-right: auto;
  display: flex;
  gap: 50px;
  padding: 30px;
  flex-wrap: wrap;
  justify-content: center;
}

.divBtn {
  background-color: grey;
  width: 140px;
  height: 140px;
}

.green-backgrond {
  background-color: green;
}

.result {
  background-color: lightsalmon;
  width: 760px;
  margin-left: auto;
  margin-right: auto;
}

.showMessage {
  width: 760px;
  height: 100px;
  background-color: brown;
  color: black;
  margin-left: auto;
  margin-right: auto;
  font-size: xx-large;
}
</style>
