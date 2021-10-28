<script setup>
import { computed, ref } from "vue";

const todos = ref([]);

const newTodo = ref ("");

const pending = computed(() => {
  return todos.value.filter((todo) => !todo.done);
});

const completed = computed(() => {
  return todos.value.filter((todo) => todo.done);
});

const addTodo = () => {
  if (newTodo.value.trim()) {
    todos.value.push({
      id: todos.value.length,
      content: newTodo.value,
      done: false,
    });
    newTodo.value = "";
  }
};

const changeStatus = (id) => {
  const todo = todos.value.find((todo) => todo.id === id);
  todo.done = !todo.done;
};


</script>

<template>
<div class="min-h-screen bg-yellow-100">
  <div class="container flex-col pt-5 mx-auto space-y-5 ">

<h1 class="text-4xl font-thin tracking-tighter text-center">My Todo App</h1>
<input @change="addTodo" v-model="newTodo" type="text" class="px-2 py-4 text-lg text-center rounded-md " placeholder="New Todo"/>

<div >
  <div class="justify-around fflex">
      <h3 class="text-lg text-center text-green-500 ">Pending Items</h3>
    <ul class="pt-2 space-y-4">
      <li v-for="todo in pending" :key="todo.id" @click="changeStatus(todo.id)" class="w-full px-2 text-center text-black duration-300 bg-white hover:cursor-pointer hover:bg-green-200 hover:text-gray-400">
        {{todo.content}}
      </li>
      
    </ul>
 




  <h3 class="text-lg text-center text-red-700">Completed Items</h3>
  <ul class="pt-2 space-y-4">
    <li v-for="todo in completed" :key="todo.id" @click="changeStatus(todo.id)" class="w-full px-2 text-center bg-white hover:cursor-pointer hover:bg-green-200 hover:text-gray-400">
     {{todo.content}}
    </li>
  </ul>  

 </div>

  </div>
</div>

</div>





</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
