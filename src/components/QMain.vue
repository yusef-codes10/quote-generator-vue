<script setup>
import { ref } from 'vue'

const quote = ref(
  " Twenty years from now you will be more disappointed by the things that you didn't do than by the ones you did do. So throw off the bowlines. Sail away from the safe harbor. Catch the trade winds in your sails. Explore. Dream. Discover.",
)
const author = ref('H. Jackson Brown Jr., P.S. ')
</script>

<template>
  <div class="quote-container">
    <div class="quote-section">{{ quote }}</div>
    <div class="author">{{ author }}</div>
    <div class="btns"></div>
  </div>
</template>

<style scoped>
.quote-container {
  width: min(700px, 80%);
  height: auto;
  background-color: var(--font-color);
  color: var(--bg-color);
  padding: 1rem 2rem;
  border: 1px solid #000;
  border-radius: 2rem;
}

.quote-section {
  font-size: clamp(2rem, 2vw + 0.25rem, 3.1rem);
  font-weight: 500;
}

.quote-section::before {
  content: '*';
}

.author {
  display: flex;
  justify-content: flex-end;
  margin: 1rem 0;
  font-size: 1.3rem;
}

.author::before {
  content: '--';
}
</style>
