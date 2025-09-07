<template>
  <input
        :type="props.type"
        :placeholder="props.placeholder"
        class="flex-1 px-3 py-2 border rounded-l-lg focus:outline-none focus:ring-2 focus:ring-orange-500"
      >
</template>

<script setup lang="ts">
const props = defineProps<{ type: string, placeholder: string }>()
</script>