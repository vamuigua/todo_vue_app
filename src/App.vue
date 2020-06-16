<template>
  <div id="app">
    <Header></Header>
    <AddTodo v-on:add-todo="addTodo"></AddTodo>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"></Todos>
  </div>
</template>

<script>
import Header from "./components/layouts/Header";
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";
const axios = require("axios").default;

export default {
  name: "App",
  components: {
    Header,
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      // get the title and completed from the newTodo
      const { title, completed } = newTodo;
      // send post request
      axios
        .post("https://jsonplaceholder.typicode.com/todos", {
          title: title,
          completed: completed
        })
        .then(response => this.todos.push(response.data))
        .catch(err => console.log(err));
    }
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=5")
      .then(response => (this.todos = response.data))
      .catch(err => console.log(err));
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
