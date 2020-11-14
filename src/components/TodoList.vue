<template>
  <div class="wrapper">
    <h1>To do List</h1>
    <input
      v-model.trim="newTodo"
      id="todoInput"
      placeholder="Please enter your to-dos"
      @keyup.enter="addTodo"
    />
    <div v-for="(todo, index) in todos" v-bind:key="todo.id" class="todoItem">
      <div>
        {{ todo.title }}
      </div>
      <div class="remove" @click="removeTodo(index)">
        &times;
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  data() {
    return {
      newTodo: "",
      idForTodo: 3,
      todos: [
        {
          id: 1,
          title: "Finish Vue Screencast",
          completed: false,
        },
        {
          id: 2,
          title: "Write velog with vue",
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.length == 0) {
        return;
      }
      this.todos.push({
        id: this.idForTodo,
        title: this.newTodo,
        completed: false,
      });
      this.newTodo = "";
      this.idForTodo++;
    },

    removeTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style lang="scss">
.wrapper {
  width: 900px;
}
h1 {
  text-align: center;
  font-weight: 600;
  font-size: 48px;
}
input {
  width: 100%;
  padding: 10px;
  margin-bottom: 12px;
  &:focus {
    outline: none;
  }
}

.todoItem {
  margin-bottom: 12px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  .remove {
    padding: 0 15px;
    cursor: pointer;
  }
}
</style>
