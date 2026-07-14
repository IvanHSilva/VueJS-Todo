<template>
  <div class="min-h-screen bg-gray-800">
    <!-- Content -->
    <div class="px-3 py-10 md:px-10">
      <div class="w-full sm:w-1/2 lg:w-1/3 mx-auto">

        <TodoSpinner />

        <TodoFormAdd />

        <TodoItems />

        <TodoEmpty />

      </div>
    </div>
    <!--/ Content -->

  </div>
</template>

<script setup>
import TodoEmpty from './components/TodoEmpty.vue';
import TodoFormAdd from './components/TodoFormAdd.vue';
import TodoItems from './components/TodoItems.vue';
import TodoSpinner from './components/TodoSpinner.vue';

</script>
