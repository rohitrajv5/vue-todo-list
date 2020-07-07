<template>
      <li>
           <div class="form-check"> <label class="form-check-label"> <input class="checkbox" type="checkbox" v-on:change="markCompleted"> {{todo.title}} <i class="input-helper"></i></label> </div> <a href="#" @click="$emit('del-todo',todo.id)"><i class="remove mdi mdi-close-circle-outline"></i></a>
       </li>
</template>

<script>
export default {
  name: "TodoItem",
  props:['todo'],  
  data() {
    return {
     
    }
  },
  methods:{
      markCompleted(){
          console.log("Completed");
          this.todo.completed = !this.todo.completed;
          this.$emit("markCompleted",this.todo.completed);
      }
  }
};
</script>

<style>

</style>
