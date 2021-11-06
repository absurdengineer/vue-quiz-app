<template>
  <div class="result">
    <div class="title">{{ title }}</div>
    <div class="desc">{{ description }}</div>
  </div>
</template>

<script>
export default {
  name: "Result",
  props: ["results", "correctAnswers"],
  computed: {
    title() {
      const result = this.results.find(
        (result) =>
          result.min <= this.correctAnswers && result.max >= this.correctAnswers
      );
      return result.title;
    },
    description() {
      const result = this.results.find(
        (result) =>
          result.min <= this.correctAnswers && result.max >= this.correctAnswers
      );
      return result.desc;
    },
  },
};
</script>

<style></style>
