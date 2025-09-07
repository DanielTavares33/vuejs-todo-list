<template>
  <div class="w-full bg-whiteshadow-lg rounded-2xl p-6">
    <Header title="📝 My To-Do List" />

    <div class="flex mb-4">
      <Input v-model="newTask" type="text" placeholder="Add a new task..." @keyup.enter="addItem" />
      <Button
        label="Add"
        textColor="text-white"
        bgColor="bg-orange-500"
        hoverBgColor="bg-orange-600"
        :clickHandler="addItem"
      />
    </div>

    <TodoList :items="items" @remove="removeTask" />
  </div>
</template>

<script setup lang="ts">
import Header from './components/Header.vue'
import Input from './components/Input.vue'
import Button from './components/Button.vue'
import TodoList from './components/TodoList.vue'

import { onMounted, ref, watch } from 'vue'

const items = ref<Array<{ id: number; text: string; completed: boolean }>>([])

const newTask = ref('')

// Load tasks from localStorage on startup
onMounted(() => {
  const savedItems = localStorage.getItem('todo-items')
  if (savedItems) {
    items.value = JSON.parse(savedItems)
  }
})

// Watch for changes and save to localStorage
watch(
  items,
  (val) => {
    localStorage.setItem('todo-items', JSON.stringify(val))
  },
  { deep: true },
)

function addItem() {
  if (!newTask.value.trim()) {
    return
  }

  const newItem = {
    id: Date.now(),
    text: newTask.value,
    completed: false,
  }
  items.value.push(newItem)
  newTask.value = ''
}

function removeTask(id: number) {
  items.value = items.value.filter((item) => item.id !== id)
}
</script>
