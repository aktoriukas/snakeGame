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
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  overflow: hidden;
}
.btn {
  border: none;
  background-color: #7b7b7b;
  color: #83e6d7;
  padding: 10px;
}
</style>
