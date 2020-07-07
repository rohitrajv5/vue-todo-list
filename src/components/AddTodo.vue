<template>
  <div>
    <div class="add-items d-flex"> <input type="text" v-model="todo" class="form-control todo-list-input" placeholder="What do you need to do today?"> <button class="add btn btn-primary font-weight-bold todo-list-add-btn" @click="addTodo()">Add</button> </div>
    </div>
</template>

<script>
export default {
  name: "AddTodo",  
  components:{
     
  },
  data() {
    return {
        todo:''
    }
  },
  methods:{
      addTodo(){
          console.log("Todo"+this.todo);
          this.$emit("add-todo",this.todo);
      }
  }
};
</script>

<style>

</style>
