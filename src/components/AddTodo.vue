<template>
  <form v-on:submit="addTodo">
    <input type="text" v-model="title" name="title" placeholder="Add Todo..." />
    <input type="submit" value="Submit" class="btn" />
  </form>
</template>

<script>
//import uuid from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false,
      };
      this.$emit("addTodo", newTodo);
      this.title = "";
    },
  },
};
</script>
