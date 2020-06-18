<template>
  <div class="about">
    <h1>VUE TODO APP 📓</h1>
    <p>
      A single page
      <b>TodoList App</b> made in Vue.js.
    </p>
    <hr class="hr-line" />
    <div class="content">
      <ul>
        <li>
          <p>Vue Router plugin was used to handle view routes.</p>
        </li>
        <li>
          <p>
            <a href="https://jsonplaceholder.typicode.com/" target="_blank">JSONPlaceholder</a> was used for sending & receiving requests for Todo items
          </p>
        </li>
      </ul>
    </div>
    <hr width="80%" style="margin:auto" />
    <div class="socials">
      <a href="https://github.com/vamuigua/todo_vue_app" target="_blank">Find the full code here!</a>
    </div>
    <i>N/B: The delete function will delete the todo items that you add because JSONPlaceholder gives the same id for each new todo item.</i>
    <br />
    <div class="socials">
      <i>
        Created with ☕ by
        <a href="https://github.com/vamuigua">Victor Allen</a>
        🐱‍👤
      </i>
    </div>
  </div>
</template>

<style scoped>
.content {
  margin: 5px 0;
  padding: 10px;
}
.hr-line {
  width: 80%;
  margin: auto;
}
.socials {
  margin: 10px;
}
</style>