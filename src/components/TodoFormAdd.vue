<template>
  <form @submit.prevent="addItem" class="flex items-center px-4 bg-gray-900 h-16 rounded-sm border-l-2
    border-green-400 mb-3">
    <input v-model="newItem" placeholder="Adicione um novo item..." type="text" class="bg-gray-900 placeholder-gray-500 text-gray-500 font-light
      focus:outline-none block w-full appearance-none leading-normal py-3 pr-3" />

    <button type="submit" class="text-green-400 text-xs font-semibold
    focus:outline-none">
      ADICIONAR
    </button>
  </form>
</template>

<script setup>
import { ref } from 'vue'

const emit = defineEmits(['add'])
const newItem = ref('')

const addItem = () => {
  if (!newItem.value.trim()) return

  emit('add', newItem.value)

  newItem.value = ''
}
</script>
