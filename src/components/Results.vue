<template>
  <p class="par">Reactoin Time: {{ score }} ms</p>
  <p class="par">{{ rank }}</p>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 370) {
      this.rank = " عالی بود فوق العاده";
    } else if (this.score < 550) {
      this.rank = "هی بد نبود";
    } else {
      this.rank = "حلزون کی بودی";
    }
  },
};
</script>

<style>
.par {
  font-size: 1.4em;
  color: rgb(247, 1, 108);
}
</style>
