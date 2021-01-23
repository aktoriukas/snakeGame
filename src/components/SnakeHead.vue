<template>
  <div id="snakeHead" v-bind:style="styles"></div>
</template>

<script>
export default {
  name: "SnakeHead",
  data() {
    return {
      styles: {
        top: `50%`,
        left: "50%",
        transform: "translate(-50%, -50%)",
      },
    };
  },
  props: ["gameIsOn", "facingDirection", "lostGame"],
  methods: {
    moveForward: function async() {
      if (!this.gameIsOn) clearInterval(this.intervalID);
      switch (this.facingDirection) {
        case 0:
          this.moveUp();
          break;
        case 1:
          this.moveRight();
          break;
        case 2:
          this.moveDown();
          break;
        case 3:
          this.moveLeft();
          break;
        default:
          break;
      }
    },
    resetSnake: function () {
      this.styles = {
        top: `50%`,
        left: "50%",
        transform: "translate(-50%, -50%)",
      };
    },
    moveUp: function () {
      let newTop = Number(this.styles.top.slice(0, -1));
      --newTop;
      this.styles.top = `${newTop}%`;
      if (newTop === 1) this.lostGame(), this.resetSnake();
    },
    moveDown: function () {
      let newTop = Number(this.styles.top.slice(0, -1));
      ++newTop;
      this.styles.top = `${newTop}%`;
      if (newTop === 99) this.lostGame(), this.resetSnake();
    },
    moveLeft: function () {
      let newLeft = Number(this.styles.left.slice(0, -1));
      --newLeft;
      this.styles.left = `${newLeft}%`;
      if (newLeft === 1) this.lostGame(), this.resetSnake();
    },
    moveRight: function () {
      let newLeft = Number(this.styles.left.slice(0, -1));
      ++newLeft;
      this.styles.left = `${newLeft}%`;
      if (newLeft === 99) this.lostGame(), this.resetSnake();
    },
    runGame: function () {
      this.intervalID = setInterval(() => {
        this.moveForward();
      }, 50);
    },
  },
  created: function () {},
};
</script>

<style scoped>
#snakeHead {
  position: absolute;
  transition: all 0.05s ease;
  width: 1vh;
  height: 1vh;
  background-color: brown;
}
</style>