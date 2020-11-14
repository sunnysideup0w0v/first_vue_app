<template>
  <div class="wrapper">
    <h1>To do List</h1>
    <input id="todoInput" placeholder="Please enter your to-dos" />
    <ul>
      <li>될까?</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  methods: {
    inputChange(e) {
      console.log(e.target.value);
    },
  },
};
</script>

<style lang="scss">
h1 {
  text-align: center;
  font-weight: 600;
  font-size: 48px;
}
input {
  width: 100%;
  padding: 10px;
}
.wrapper {
  width: 960px;
}
</style>
