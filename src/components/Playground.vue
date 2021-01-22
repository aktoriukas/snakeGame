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
          ++this.facingDirection;
          break;

        case 37:
          //left
          --this.facingDirection;
          this.facingDirection < 0 ? (this.facingDirection = 3) : "";
          break;

        case 38:
          //up
          break;

        case 40:
          //down
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