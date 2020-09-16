<template>
  <FlexboxLayout justifyContent="space-between">
    <Star
      v-for="index in 5"
      v-bind="starStyles"
      :value="getStarValue(index)"
      :key="index"
      @tap="emitRating"
    />
  </FlexboxLayout>
</template>

<script>
import Star from "./Star";

export default {
  name: "StarRating",

  props: {
    value: {
      type: Number,
      required: true,
      value: 0
    },
    size: {
      type: [String, Number],
      required: false,
      default: 30
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
    outlineColor: {
      type: String,
      required: false,
      default: "#000"
    }
  },

  components: {
    Star
  },

  computed: {
    starStyles() {
      return {
        size: this.size,
        fillColor: this.fillColor,
        emptyColor: this.emptyColor,
        outlineColor: this.outlineColor
      };
    }
  },

  methods: {
    getStarValue(starIndex) {
      return starIndex <= this.value
        ? 1
        : starIndex - this.value < 1
        ? this.value % 1
        : 0;
    },

    emitRating(value) {
      this.$emit("ratingSelected", value);
    }
  }
};
</script>