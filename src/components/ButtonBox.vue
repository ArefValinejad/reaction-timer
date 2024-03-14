<template>
  <div class="container">
    <div
      class="divBtn"
      :class="{ 'green-backgrond': item === 5 }"
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
    return {};
  },
  methods: {
    handelClick(id) {
      console.log(id);
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
</style>
