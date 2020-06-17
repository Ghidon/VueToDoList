<template>
  <div>
    <!-- We are looping here through the todos to check if they
      are imported correctly as props. to do that, we also have
      to bind the loop to a key value (like in react)
    which will be a unique value (id in this case)-->
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo',
       todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  //   passing todos as props into the components
  props: ["todos"]
};
</script>

<style scoped>
</style>