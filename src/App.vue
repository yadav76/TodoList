<template>
  <TodoComp />
</template>

<script>
import TodoComp from "./components/TodoComp.vue";
export default {
  name: "App",
  components: {
    TodoComp,
  },
};
</script>

<style>
#app {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
