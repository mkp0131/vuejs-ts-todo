<template>
  <div>
    <h1>✅ TODO APP</h1>
    <TodoForm :todoTxt="todoTxt" @input="updateTodoTxt" @add="addTodoItem" />
    <ul v-for="(todo, index) in todos" :key="index">
      <li>{{ todo }}</li>
    </ul>
    <input type="text" v-model="test" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import TodoForm from './components/TodoForm.vue';

interface ITodo {
  todoTxt: string;
  todos: string[];
  test: string;
}

export default Vue.extend({
  data(): ITodo {
    return {
      todoTxt: '',
      todos: [],
      test: '',
    };
  },
  methods: {
    updateTodoTxt(todoTxt: string) {
      this.todoTxt = todoTxt;
    },
    addTodoItem() {
      const txt = this.todoTxt;
      this.todos.push(txt);
      this.todoTxt = '';
    },
  },
  components: { TodoForm },
});
</script>

<style scoped></style>
