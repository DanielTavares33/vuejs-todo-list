<template>
  <button
    :class="`px-4 py-2 rounded-r-lg ${hoverBgColor} cursor-pointer ${props.textColor} ${props.bgColor}`"
    @click="props.clickHandler"
  >
    {{ props.label }}
  </button>
</template>

<script setup lang="ts">
const props = defineProps<{
  label: string
  textColor: string
  bgColor: string
  hoverBgColor: string
  clickHandler: () => void
}>()
const hoverBgColor = `hover:${props.hoverBgColor}`
</script>
