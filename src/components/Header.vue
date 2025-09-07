<template lang="">
  <h1 class="text-2xl font-bold mb-4">{{ props.title }}</h1>
</template>

<script setup lang="ts">
const props = defineProps<{ title: string }>()
</script>
