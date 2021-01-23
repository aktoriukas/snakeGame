<template>
  <div class="you-lost">
    <div class="inner">
      <h2>You Lost</h2>
      <button v-on:click="$emit('restartGame')" class="btn">Try Again?</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "YouLost",
  methods: {},
};
</script>

<style scoped>
.you-lost {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.inner {
  width: 10rem;
  height: 10rem;
  margin: auto;
  background: brown;
  text-align: center;
  color: aliceblue;
}
</style>