<script setup>
import QHeader from './components/QHeader.vue'
import QMain from './components/QMain.vue'
</script>

<template>
  <div class="container">
    <QHeader />
    <QMain />
  </div>
</template>

<style scoped>
.container {
  height: 100dvh;
  background-color: var(--bg-color);
  color: var(--font-color);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
