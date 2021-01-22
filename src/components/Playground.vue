<template>
  <div id="playground">
    <Snake-head
      v-bind:gameIsOn="gameIsOn"
      v-bind:facingDirection="facingDirection"
      v-bind:lostGame="lostGame"
    />
  </div>
</template>

<script>
import SnakeHead from "./SnakeHead.vue";
export default {
  name: "Playground",
  components: {
    SnakeHead,
  },
  data() {
    return {
      gameIsOn: true,
      facingDirection: 0,
    };
  },
  methods: {
    keyPressed: function (e) {
      switch (e.keyCode) {
        case 39:
          //right
          this.facingDirection = 1;
          break;

        case 37:
          //left
          this.facingDirection = 3;
          break;

        case 38:
          //up
          this.facingDirection = 0;
          break;

        case 40:
          //down
          this.facingDirection = 2;
          break;

        default:
          break;
      }
    },
    lostGame() {
      this.gameIsOn = false;
    },
  },
  created() {
    window.addEventListener("keyup", (e) => this.keyPressed(e));
  },
};
</script>

<style scoped>
#playground {
  background: cadetblue;
  width: 100%;
  height: 100%;
  border: 10px solid black;
}
</style>