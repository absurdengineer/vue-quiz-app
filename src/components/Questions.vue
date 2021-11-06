<template>
  <div class="questions-ctr">
    <div class="progress">
      <div
        class="bar"
        :style="{ width: `${(questionAnswered / questions.length) * 100}%` }"
      ></div>
      <div class="status">
        {{ questionAnswered }} out of {{ questions.length }} questions answered
      </div>
    </div>
    <div class="single-question">
      <div class="question">{{ questions[questionAnswered].q }}</div>
      <div class="answers">
        <div
          class="answer"
          v-for="answer in questions[questionAnswered].answers"
          :key="answer.text"
          @click="this.$emit('answered', answer.is_correct)"
        >
          {{ answer.text }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Questions",
  props: ["questionAnswered", "questions"],
};
</script>

<style></style>
