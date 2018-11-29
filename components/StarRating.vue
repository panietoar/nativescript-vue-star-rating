<template>
  <FlexboxLayout justifyContent="space-between">
    <Star 
      v-for="index in 5"
      :size="size"
      :borderColor="borderColor"
      :fillColor="fillColor"
      :emptyColor="emptyColor"
      :value="getStarValue(index)"
      :key="index"/>
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
      type: Number,
      required: false,
      default: 75
    },
    borderColor: {
      type: String,
      required: false,
      default: "#000"
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
  },

  components: {
    Star
  },

  methods: {
    getStarValue(starIndex) {
      return starIndex <= this.value ? 1 : starIndex - this.value < 1 ? 1 : 0;
    }
  }
}
</script>

<style>

</style>
