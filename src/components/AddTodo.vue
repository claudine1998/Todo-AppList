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
// import Vue from 'vue';
// import UUID from 'vue-uuid';
import { uuid } from 'vue-uuid';
export default {
  name: 'AddTodo',
  data() {
    return {
      title: '',
      uuid: uuid.v1()    }
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodoObj = {
        //  id: "13465232",
        //  id: String(Vue.use(UUID)),
        id: uuid.v1(),
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