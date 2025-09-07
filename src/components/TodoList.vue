<template>
  <ul class="space-y-3">
      <!-- Item -->
      <li class="flex items-center justify-between bg-gray-50 dark:bg-gray-800 p-3 rounded-lg shadow-sm">
        <div class="flex items-center gap-2">
          <input type="checkbox" class="size-5 rounded text-blue-500 focus:ring-0">
          <span>Finish TailwindCSS layout</span>
        </div>
        <button class="text-red-500 hover:text-red-700">✕</button>
      </li>

      <li class="flex items-center justify-between bg-gray-50 dark:bg-gray-800 p-3 rounded-lg shadow-sm">
        <div class="flex items-center gap-2">
          <input type="checkbox" class="size-5 rounded text-blue-500 focus:ring-0" checked>
          <span class="line-through text-gray-400">Write documentation</span>
        </div>
        <button class="text-red-500 hover:text-red-700">✕</button>
      </li>
    </ul>
</template>

<script setup lang="ts">

</script>