<template>
  <p :class="todo.done ? 'done' : ''">
    <input type="checkbox" v-model="todo.done"/>
    {{ todo.description }}
  </p>
</template>

<script>
export default {
  props: ['todo']
}
</script>

<style scoped>
p {
  font-size: 32pt;
  font-weight: bold
}

p.done {
  text-decoration: line-through;
  color:lightgray;
}
</style>
