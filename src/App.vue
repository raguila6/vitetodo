<script setup>
import Title from "./components/Title.vue"
import ListsVue from "./components/Lists.vue";

import useTodos  from "./composables/useTodos";
import Lists from "./components/Lists.vue";

</script>

<template >
  
<div class="min-h-screen bg-yellow-200">
<Title/>

  <div> 
  <Lists/>
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
