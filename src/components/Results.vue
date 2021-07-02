<template>
  <p>Score is {{ score }}</p>
  <p class="rank">{{ rank }}</p>
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
    if (this.score < 250) {
      this.rank = "Awesome!!";
    } else if (this.score < 450 && this.score >= 250) {
      this.rank = "Not Bad..";
    } else {
      this.rank = "Snails pace :(";
    }
  },
};
</script>

<style>
.rank {
  color: lightgreen;
  font-size: 1.5em;
}
</style>