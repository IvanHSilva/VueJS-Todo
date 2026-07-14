<template>
    <div class="space-y-2">
        <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" />
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
</script>
