<script setup>
import { ref, onMounted } from 'vue'

const quote = ref("If you tell the truth, you don't have to remember anything.")
const author = ref('Mark Twain')

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
  {
    index: 11,
    quote: 'Be the change that you wish to see in the world.',
    author: 'Mahatma Gandhi',
  },
  {
    index: 12,
    quote:
      "If you want to know what a man's like, take a good look at how he treats his inferiors, not his equals.",
    author: 'J.K. Rowling',
  },
  {
    index: 13,
    quote:
      "Imperfection is beauty, madness is genius and it's better to be absolutely ridiculous than absolutely boring.",
    author: 'Marilyn Monroe',
  },
])

const generateQuote = () => {
  const randomIndex = Math.floor(Math.random() * quotes.value.length)
  const randomQuote = quotes.value[randomIndex]
  quote.value = randomQuote.quote
  author.value = randomQuote.author
}
// fetch therandom quotes
onMounted(async () => {
  try {
    // fetch
    const response = await fetch('https://api.api-ninjas.com/v1/quotes', {
      headers: {
        'X-Api-Key': import.meta.env.VITE_API_NINJAS_KEY,
      },
    })

    // turn into json
    const data = response.json()
  } catch (error) {
    console.log(error)
  }
})
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
  min-height: 300px;
  background-color: var(--font-color);
  color: var(--bg-color);
  padding: 1rem 2rem;
  border: 1px solid #000;
  border-radius: 2rem;

  display: flex;
  flex-direction: column;
}

.quote-section {
  font-size: clamp(2rem, 2vw + 0.25rem, 3.1rem);
  font-weight: 500;
  flex: 1;
}

.quote-section::before {
  content: '“ ';
  font-weight: 700;
}

.quote-section::after {
  content: '”';
  font-weight: 700;
}

.author {
  /* display: flex; */
  align-self: flex-end;
  margin: 1rem 0;
  font-size: 1.3rem;
}

.author::before {
  content: '--';
}

.btns {
  align-self: flex-end;
}

button {
  padding: 12px 16px;
  background-color: var(--bg-color);
  color: var(--font-color);
  border: none;
  border-radius: 0.5rem;
  cursor: pointer;
  font-size: 1.4rem;
}
</style>
