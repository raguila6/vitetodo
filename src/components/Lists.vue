<script setup>
import useTodos from '../composables/useTodos';

const {pending, completed, changeStatus} = useTodos();


</script>

<template>
<div class="bg-blue-600">
<div class="flex-auto">
      <h3 class="text-lg text-center text-green-500 ">Pending</h3>
    <ul class="pt-2 space-y-4" >
      <li v-for="todo in pending" :key="todo.id" @click="changeStatus(todo.id)" class="w-full px-2 text-center text-black duration-300 bg-white hover:cursor-pointer hover:bg-green-200 hover:text-gray-400">
        {{todo.content}}
      </li>
      
    </ul>
    </div>
 <div class="flex-auto">
  <h3 class="text-lg text-center text-red-700">Completed Items</h3>
  <ul class="pt-2 space-y-4">
    <li v-for="todo in completed" :key="todo.id" @click="changeStatus(todo.id)" class="w-full px-2 text-center bg-white hover:cursor-pointer hover:bg-grey-200 hover:text-gray-400">
     {{todo.content}}
    </li>
  </ul>  
</div>

</div>

 


</template>