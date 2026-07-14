<template>
    <div class="bg-gray-300 rounded-sm">
        <div class="flex items-center px-4 py-3 border-b border-gray-400">

            <!-- Botão concluir -->
            <div class="flex items-center justify-center mr-2">
                <button :class="todo.completed ? 'text-green-600' : 'text-gray-400'">
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                </button>
            </div>

            <!-- Texto da tarefa -->
            <div class="w-full">
                <input type="text" :value="todo.title" readonly :class="[
                    'bg-gray-300 placeholder-gray-500 text-gray-700 font-light focus:outline-none block w-full',
                    todo.completed ? 'line-through' : ''
                ]">
            </div>

            <!-- Excluir -->
            <div class="ml-auto flex items-center justify-center">
                <button class="text-gray-500">
                    🗑
                </button>
            </div>

        </div>
    </div>
</template>

<script setup>
defineProps({
    todo: {
        type: Object,
        required: true
    }
})
</script>