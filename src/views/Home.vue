<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo"></AddTodo>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"></Todos>
  </div>
</template>

<script>
import Todos from "../components/Todos";
import AddTodo from "../components/AddTodo";
const axios = require("axios").default;

export default {
  name: "Home",
  components: {
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
      // delete request to remove a todoitem
      axios
        .delete("https://jsonplaceholder.typicode.com/todos/" + id)
        .then((this.todos = this.todos.filter(todo => todo.id !== id)))
        .catch(err => console.log(err));
    },
    addTodo(newTodo) {
      // get the title and completed from the newTodo
      const { title, completed } = newTodo;
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
    // get 5 todos from jsonplaceholder
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
