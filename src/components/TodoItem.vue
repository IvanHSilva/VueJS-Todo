<template>
  <div class="bg-gray-300 rounded-sm">
    <div class="flex items-center px-4 py-3 border-b border-gray-400">

      <!-- Botão concluir -->
      <div class="flex items-center justify-center mr-2">
        <button @click="toggleComplete" :class="todo.completed ? 'text-green-600' : 'text-gray-400'">
          ✓
        </button>
      </div>

      <!-- Texto editável -->
      <div class="w-full">
        <input v-model="title" @keyup.enter="save" @blur="save" type="text"
          class="bg-gray-300 text-gray-700 font-light focus:outline-none block w-full"
          :class="todo.completed ? 'line-through' : ''">
      </div>

      <!-- Excluir -->
      <div class="ml-auto">
        <button class="text-gray-500">
          🗑
        </button>
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const props = defineProps({
  todo: {
    type: Object,
    required: true
  }
})

const emit = defineEmits(['update'])

const title = ref(props.todo.title)

const save = () => {
  const newTitle = title.value.trim()

  // Campo vazio: volta para o valor anterior
  if (!newTitle) {
    title.value = props.todo.title
    return
  }

  // Não salva se não houve alteração
  if (newTitle === props.todo.title) return

  emit('update', {
    ...props.todo,
    title: newTitle
  })
}

const toggleComplete = () => {
  emit('update', {
    ...props.todo,
    completed: !props.todo.completed
  })
}
</script>
