<template>
  <div class="page-content page-container" id="page-content">
    <div class="padding">
        <div class="row container d-flex justify-content-center">
            <div class="col-lg-12">
                <div class="card px-3">
                    <div class="card-body">
                        <Header></Header>
                        <AddTodo v-on:add-todo="addTodo($event)"></AddTodo>
                        <div class="list-wrapper">
                            <Todos :todos="todos" v-on:del-todo="deleteTodo"></Todos>                          
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header/Header.vue";
import Todos from "./components/Todos.vue";
import AddTodo from "./components/AddTodo.vue";
import uuid from 'uuid';

export default {
  name: "App",
  components: {   
    Todos,
    AddTodo,
    Header
  },
  data() {
    return {
      todos: [
        {
          userId: 1,
          id: 1,
          title: "delectus aut autem",
          completed: false
        },
        {
          userId: 1,
          id: 2,
          title: "quis ut nam facilis et officia qui",
          completed: false
        },
        {
          userId: 1,
          id: 3,
          title: "fugiat veniam minus",
          completed: false
        },
        {
          userId: 1,
          id: 4,
          title: "et porro tempora",
          completed: true
        }
      ],
      newtodo:{
          userId: "",
          id: "",
          title: "",
          completed: ""
      }
    }
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id != id);
    },
    addTodo(event){
      this.newtodo.userId = 1;
      this.newtodo.id = uuid.v4();
      this.newtodo.title = event;
      this.newtodo.completed = false;
      this.todos.push(this.newtodo);
    }
  }
};
</script>

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
