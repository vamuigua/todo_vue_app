<template>
  <div class="about">
    <h1>VUE TODO PROJECT</h1>
    <p>
      A single page
      <b>TodoList App</b> made in Vue.js.
    </p>
    <hr class="hr-line" />
    <div class="content">
      <ul>
        <li>
          <p>Vue Router plugin was added to handle routes of the Home & About Page.</p>
        </li>
        <li>
          <p>
            <a href="https://jsonplaceholder.typicode.com/" target="_blank">JSONPlaceholder</a> was used to for sending & receiving requests for Todos
          </p>
        </li>
      </ul>
    </div>
    <hr width="80%" style="margin:auto" />
    <div class="socials">
      <a href="https://github.com/vamuigua/todo_vue_app" target="_blank">Find the full code here!</a>
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
</style>