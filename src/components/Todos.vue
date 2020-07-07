<template>
  <div>
    <ul class="d-flex flex-column-reverse todo-list" v-for="todo in todos" v-bind:key="todo.id" :class="{'completed':todo.completed}" @input="markCompleted = $event">
            <TodoItem :todo="todo" v-on:del-todo="$emit('del-todo',todo.id)"></TodoItem>                                 
        </ul>
    </div>
</template>

<script>

import TodoItem from "./TodoItem.vue";

export default {
  name: "Todos",
  props:['todos'],
  components:{
      TodoItem
  },
  data() {
    return {
     
    }
  }
};
</script>

<style>

</style>
