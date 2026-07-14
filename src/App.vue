<template>
  <div class="min-h-screen bg-gray-800">
    <!-- Content -->
    <div class="px-3 py-10 md:px-10">
      <div class="w-full sm:w-1/2 lg:w-1/3 mx-auto">

        <TodoSpinner v-if="loading" />

        <TodoFormAdd />

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

import TodoEmpty from './components/TodoEmpty.vue';
import TodoFormAdd from './components/TodoFormAdd.vue';
import TodoItems from './components/TodoItems.vue';
import TodoSpinner from './components/TodoSpinner.vue';

const todos = ref([])
const loading = ref(true)

onMounted(async () => {
  try {
    const response = await api.get('/todos')

    console.log(response.data) // teste

    todos.value = response.data
  } catch (error) {
    console.error(error)
  } finally {
    loading.value = false
  }
})
</script>
