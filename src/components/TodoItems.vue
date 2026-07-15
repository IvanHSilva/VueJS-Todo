<template>
  <div class="space-y-2">
    <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" @update="$emit('update', $event)"
      @delete="$emit('delete', $event)" />
  </div>
</template>

<script setup>
import TodoItem from './TodoItem.vue'

defineProps({
  todos: {
    type: Array,
    required: true
  }
})

defineEmits(['update', 'delete'])
</script>
