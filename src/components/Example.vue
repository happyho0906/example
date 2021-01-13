<template>
  <div>
    <vue-p5 @setup="setup" @draw="draw" @mouseclicked="mouseClicked"> </vue-p5>
  </div>
</template>

<script>
import VueP5 from "vue-p5";

export default {
  name: "p5-example",
  components: {
    "vue-p5": VueP5,
  },
  data: () => ({
    fill: 255,
  }),
  computed: {},
  methods: {
    setup(sketch) {
      sketch.createCanvas(400, 400);
    },
    draw(sketch) {
      sketch.fill(this.fill);
      sketch.ellipse(sketch.pmouseX, sketch.pmouseY, 80, 80);
    },
    toggleFill() {
      this.fill = 255 - this.fill;
    },
    mouseClicked() {
      this.toggleFill();
    }
  }
};
</script>
