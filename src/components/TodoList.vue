<template>
  <ul class="space-y-3">
    <!-- Item -->
    <li
      class="flex items-center justify-between p-3 rounded-lg shadow-sm"
      v-for="item in props.items"
      :key="item.id"
    >
      <div class="flex items-center gap-2">
        <input
          type="checkbox"
          class="size-5 rounded accent-orange-500 focus:ring-0 cursor-pointer"
          @change="toggleCompletion(item.id)"
        />
        <span :class="{ 'line-through text-gray-400': item.completed }">{{ item.text }}</span>
      </div>
      <button
        class="text-red-500 hover:text-red-700 cursor-pointer"
        @click="emit('remove', item.id)"
      >
        ✕
      </button>
    </li>
  </ul>
</template>

<script setup lang="ts">
const props = defineProps<{ items: Array<{ id: number; text: string; completed: boolean }> }>()
const emit = defineEmits<{ (e: 'remove', id: number): void }>()

function toggleCompletion(id: number) {
  const item = props.items.find((item) => item.id === id)
  if (item) {
    item.completed = !item.completed
  }
}
</script>
