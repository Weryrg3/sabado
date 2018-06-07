<template>
  <div>
    <input type="text"
    v-model="currentTodo"
    v-on:keyup.enter="addTodo"
    />
    <button @click="clearTodos">Clear todos</button>
    <Todo
    v-for="todo in todos"
    :key="todo.description"
    :todo="todo"/>
  </div>
</template>

<script>
import Todo from './components/Todo'

export default {
  components: {Todo},
  data() {
    return {
      currentTodo: '',
      todos: []
    }
  },
  methods: {
    addTodo() {
      if (this.currentTodo !== '') {
        let todo = {description: this.currentTodo, done: false}
        this.todos.push(todo)
        this.currentTodo = ''
      }
    },
    clearTodos() {
      this.todos = this.todos.filter(todo => !todo.done)
    }
  },
  created() {
    console.log('test')
  }
}
</script>
