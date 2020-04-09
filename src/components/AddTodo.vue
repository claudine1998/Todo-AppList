<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title">
      <button type="submit">Add</button>
    </form>
  </div>
</template>
<script>
//import uuid from 'uuid';
import Vue from 'vue';
import UUID from 'vue-uuid';

console.log("TEST :" + Vue.use(UUID));
export default {
  name: 'AddTodo',
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodoObj = {
          
         // id: "13465232",
         id: String(Vue.use(UUID)),
        title: this.title,
        completed: false
      }
      this.$emit('add-todo', newTodoObj);
      this.title = '';
    }
  }
}
</script>
<style scoped>
</style>