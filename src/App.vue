<template>
  <div class="w-full max-w-md bg-whiteshadow-lg rounded-2xl p-6">
    <Header title="📝 My To-Do List" />

    <div class="flex mb-4">
      <Input type="text" placeholder="Add a new task..." />
      <Button label="Add" textColor="text-white" bgColor="bg-orange-500" hoverBgColor="bg-orange-600" />
    </div>
  </div>
</template>

<script setup lang="ts">
import Header from './components/Header.vue'
import Input from './components/Input.vue'
import Button from './components/Button.vue'
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
