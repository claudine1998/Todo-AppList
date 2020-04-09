<template>
  <div v-bind:class="{ 'completed': todo.completed }">
    <p v-on:click="markComplete">{{ todo.title }}</p>
    <!-- <p v-on:click="markComplete">{{ todo.id }}</p> -->
    <button @click="$emit('delete-todo', todo.id)">Delete</button>
    <!-- <span @click="remove(todo.id)" class ="remove">x</span> -->
  </div>
</template>
<script>
export default {
  name: 'Todo',
  props: [
    "todo"
  ],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>
<style scoped>
  .completed {
    text-decoration: line-through;
  }
</style>