<template>
  <div class="questions">
    <div v-for="card in trivia" :key="card.id">
      <flash-card :card="card" @toggle="handleToggle" />
    </div>
  </div>
</template>

<script>
import trivia from "../trivia";
import FlashCard from "./FlashCard";

export default {
  components: { FlashCard },

  data() {
    return {
      trivia: [...trivia]
    };
  },

  methods: {
    handleToggle(card) {
      card.answerShown = !card.answerShown;
    }
  }
};
</script>

<style scoped>
.questions {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>
