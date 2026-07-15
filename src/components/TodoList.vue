<template>
  <div class="min-h-screen bg-gray-800">
    <!-- Content -->
    <div class="px-3 py-10 md:px-10">
      <div class="w-full sm:w-1/2 lg:w-1/3 mx-auto">

        <TodoSpinner v-if="loading" />

        <TodoFormAdd @add="addTodo" />

        <TodoItems v-if="todos.length" :todos="todos" />

        <TodoEmpty v-else />

      </div>
    </div>
    <!--/ Content -->

  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import api from '@/services/api'

import TodoEmpty from './TodoEmpty.vue';
import TodoFormAdd from './TodoFormAdd.vue';
import TodoItems from './TodoItems.vue';
import TodoSpinner from './TodoSpinner.vue';

const todos = ref([])
const loading = ref(true)

const addTodo = async (title) => {
  const newId = todos.value.length
    ? Math.max(...todos.value.map(todo => Number(todo.id))) + 1
    : 1

  const response = await api.post('/todos', {
    id: newId,
    title: title,
    completed: false
  })

  todos.value.push(response.data)
}

onMounted(async () => {
  try {
    const response = await api.get('/todos')
    todos.value = response.data
  } catch (error) {
    console.error(error)
  } finally {
    loading.value = false
  }
})
</script>
