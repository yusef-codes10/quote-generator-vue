<script setup>
import { ref } from 'vue'

const quote = ref(
  " Twenty years from now you will be more disappointed by the things that you didn't do than by the ones you did do. So throw off the bowlines. Sail away from the safe harbor. Catch the trade winds in your sails. Explore. Dream. Discover.",
)
const author = ref('H. Jackson Brown Jr., P.S. ')

// const quote = ref('')
// const author = ref('')

const quotes = ref([
  {
    index: 1,
    quote: 'Imagination is more important than knowledge.',
    author: 'Albert Einstein',
  },
  {
    index: 2,
    quote: 'Science is a way of thinking much more than it is a body of knowledge.',
    author: 'Carl Sagan',
  },
  {
    index: 3,
    quote: 'If you want to find the secrets of the universe, think in terms of energy.',
    author: 'Nikola Tesla',
  },
  {
    index: 4,
    quote: 'What we know is a drop, what we don’t know is an ocean.',
    author: 'Isaac Newton',
  },
  {
    index: 5,
    quote: 'In matters of conscience, the law of the majority has no place.',
    author: 'Mahatma Gandhi',
  },
  {
    index: 6,
    quote: 'Those who deny freedom to others deserve it not for themselves.',
    author: 'Abraham Lincoln',
  },
  {
    index: 7,
    quote: 'Power tends to corrupt, and absolute power corrupts absolutely.',
    author: 'Lord Acton',
  },
  {
    index: 8,
    quote: 'The good thing about science is that it’s true whether or not you believe in it.',
    author: 'Neil deGrasse Tyson',
  },
  {
    index: 9,
    quote: 'Man is condemned to be free.',
    author: 'Jean-Paul Sartre',
  },
  {
    index: 10,
    quote: 'A lie told often enough becomes the truth.',
    author: 'Vladimir Lenin',
  },
])

const generateQuote = () => {
  const randomIndex = Math.floor(Math.random() * quotes.value.length)
  const randomQuote = quotes.value[randomIndex]
  quote.value = randomQuote.quote
  author.value = randomQuote.author
}
</script>

<template>
  <div class="quote-container">
    <div class="quote-section">{{ quote }}</div>
    <div class="author">{{ author }}</div>
    <div class="btns">
      <button @click="generateQuote">New Quote</button>
    </div>
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
  /* display: flex; */
  justify-self: flex-end;
  margin: 1rem 0;
  font-size: 1.3rem;
}

.author::before {
  content: '--';
}

.btns {
  justify-self: flex-end;
}

button {
  padding: 12px 16px;
  background-color: var(--bg-color);
  color: var(--font-color);
  border: none;
  border-radius: 0.5rem;
  cursor: pointer;
}
</style>
