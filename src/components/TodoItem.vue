<template>
  <div class="bg-gray-300 rounded-sm">
    <div class="flex items-center px-4 py-3 border-b border-gray-400">

      <!-- Botão completar -->
      <div class="flex items-center justify-center mr-2">
        <button @click="toggleComplete" :class="todo.completed ?
          'text-green-600' : 'text-gray-400'">
          ✓
        </button>
      </div>

      <!-- Texto da tarefa -->
      <div class="w-full">
        <input v-model="title" @keyup.enter="save" @blur="save" type="text" :class="[
          'bg-gray-300 focus:outline-none block w-full',
          todo.completed
            ? 'text-black font-bold'
            : 'text-gray-700 font-light'
        ]">
      </div>

      <!-- Botão excluir -->
      <div class="ml-auto">
        <button @click="removeTodo" class="text-gray-500">
          🗑
        </button>
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref, watch } from 'vue'

const props = defineProps({
  todo: {
    type: Object,
    required: true
  }
})

const emit = defineEmits(['update', 'delete'])

const title = ref(props.todo.title)
watch(
  () => props.todo.title,
  (newTitle) => {
    title.value = newTitle
  }
)

const save = () => {
  const newTitle = title.value.trim()

  if (!newTitle) {
    title.value = props.todo.title
    return
  }

  if (newTitle === props.todo.title) return

  emit('update', {
    ...props.todo,
    title: newTitle
  })
}

const removeTodo = () => {
  emit('delete', props.todo.id)
}

const toggleComplete = () => {
  emit('update', {
    ...props.todo,
    completed: !props.todo.completed
  })
}
</script>
