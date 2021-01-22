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
  props: ["gameIsOn", "facingDirection"],
  methods: {
    moveForward: function async() {
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
    moveUp: function () {
      let newTop = Number(this.styles.top.slice(0, -1));
      this.styles.top = `${--newTop}%`;
    },
    moveDown: function () {
      let newTop = Number(this.styles.top.slice(0, -1));
      this.styles.top = `${++newTop}%`;
    },
    moveLeft: function () {
      let newLeft = Number(this.styles.left.slice(0, -1));
      this.styles.left = `${--newLeft}%`;
    },
    moveRight: function () {
      let newLeft = Number(this.styles.left.slice(0, -1));
      this.styles.left = `${++newLeft}%`;
    },
    // getDigit: function (transform, nr) {
    //   const newTransf = transform.split(",")[nr];
    //   let number = "";
    //   for (let i = 0; i < newTransf.length; i++) {
    //     if (newTransf[i] == "-" || !isNaN(Number(newTransf[i]))) {
    //       number += newTransf[i];
    //     } else if (newTransf[i] === "%") return number;
    //   }
    // },
  },
  created() {
    setInterval(() => {
      this.moveForward();
    }, 500);
  },
};
</script>

<style scoped>
#snakeHead {
  position: absolute;
  width: 1vh;
  height: 1vh;
  background-color: brown;
}
</style>