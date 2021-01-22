<template>
  <div id="app">
    <Playground />
  </div>
</template>

<script>
import Playground from "./components/Playground";
export default {
  name: "App",
  components: {
    Playground,
  },
};
</script>

<style>
html,
body,
#app {
  width: 100vh;
  height: 100vh;
  margin: 0;
  padding: 0;
}
</style>
