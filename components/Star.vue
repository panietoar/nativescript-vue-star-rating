<template>
  <StackLayout class="outline" :style="outlineStyle">
    <Button class="star" :style="starStyle" @tap="emitRating"></Button>
  </StackLayout>
</template>

<script>
export default {
  name: "Star",

  props: {
    size: {
      type: [String, Number],
      required: false,
      default: 75
    },
    fillColor: {
      type: String,
      required: false,
      default: "#FFEB0A"
    },
    emptyColor: {
      type: String,
      required: false,
      default: "#ABABAB"
    },
    value: {
      type: Number,
      required: false,
      default: 1
    },
    outlineColor: {
      type: String,
      required: false,
      default: "#000"
    }
  },

  computed: {
    starStyle() {
      return {
        width: `${this.size}px`,
        height: `${this.size}px`,
        background: `linear-gradient(90deg, ${this.fillColor} ${
          this.percentage
        }, ${this.emptyColor} ${this.percentage})`
      };
    },

    outlineStyle() {
      return {
        backgroundColor: this.outlineColor
      };
    },

    percentage() {
      return `${this.value * 100}%`;
    }
  },

  methods: {
    emitRating() {
      this.$emit("tap", this.$vnode.key);
    }
  }
};
</script>

<style lang="scss" scoped>
.star,
.outline {
  clip-path: polygon(
    50% 0%,
    61% 35%,
    100% 35%,
    68% 57%,
    79% 91%,
    50% 70%,
    21% 91%,
    32% 57%,
    0% 35%,
    39% 35%
  );
}
</style>