<template>
  <div class="todo-app">
    <h1>Todo List</h1>
    <div class="todo-form">
      <input
        type="text"
        v-model="newTodo"
        placeholder="add a new todo..."
        @keyup.enter="addTodo"
      />
      <button @click="addTodo">Add</button>
    </div>
    <ul class="todo-list">
      <li v-for="(todo, index) in todos" :key="index" class="todo-item">
        <span class="todo-text">{{ todo }}</span>
        <button @click="removeTodo(index)">Remove</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoComp",
  data() {
    return {
      newTodo: "",
      todos: [],
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() !== "") {
        this.todos.push(this.newTodo.trim());
        this.newTodo = "";
      }
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
.todo-app {
  font-family: "Poppins", sans-serif;
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
.todo-form {
  margin-bottom: 20px;
}
.todo-form input[type="text"] {
  padding: 8px;
  width: 75%;
  border-radius: 5px;
  border: 1px solid #ccc;
}
.todo-form button {
  padding: 8px 18px;
  border: none;
  background-color: #007bff;
  color: #fff;
  border-radius: 5px;
  cursor: pointer;
  margin: 0 10px;
}
.todo-list {
  list-style-type: none;
  padding: 0;
}
.todo-list li {
  margin-bottom: 10px;
}

.todo-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #f9f9f9;
  padding: 10px;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin-bottom: 10px;
}
.todo-text {
  flex: 1;
}
.todo-list button {
  padding: 4px 8px;
  border: none;
  background-color: #dc3545;
  color: #fff;
  border-radius: 5px;
  cursor: pointer;
}
</style>
