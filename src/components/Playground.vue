<template>
  <div id="playground">
    <Snake-head
      v-bind:gameIsOn="gameIsOn"
      v-bind:facingDirection="facingDirection"
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
    // checkGame: async (gameIsOn) => {
    //   console.log(gameIsOn);
    // },
    keyPressed(e) {
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
  },
  created() {
    // this.checkGame(this.gameIsOn);
    window.addEventListener("keyup", (e) => this.keyPressed(e));
  },
};
</script>

<style scoped>
#playground {
  background: cadetblue;
  width: 100vh;
  height: 100vh;
}
</style>