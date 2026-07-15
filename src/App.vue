<template>
  <div class="min-h-screen bg-gray-800">
    <div class="px-3 py-10 md:px-10">
      <div class="w-full sm:w-1/2 lg:w-1/3 mx-auto">
        <TodoList />
      </div>
    </div>
  </div>
</template>

<script setup>
import TodoList from './components/TodoList.vue'
</script>
