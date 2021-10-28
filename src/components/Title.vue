<script setup>
import { ref } from "vue";
import useTodos from "../composables/useTodos";

const {addTodo} = useTodos();

const newTodo = ref("");

const add = () => {
    if (newTodo.value){
      addTodo(newTodo.value);
      newTodo.value = "";
    }
};

</script>

<template>
    <h1 class="text-4xl font-thin tracking-tighter text-center bg-gray-100 ">My Todo App</h1>

<input @change="add" v-model="newTodo" type="text" class="px-2 py-4 text-lg text-center bg-yellow-400 rounded-md " placeholder="New Todo"/>

</template>