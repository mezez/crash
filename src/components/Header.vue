<template>
  <header>
    <h1>{{ title }}</h1>

    <!--button is displayed using the computed property in the scripts below. only shoy add task on homepage -->
    <Button
      v-show="homePage"
      @btn-click="$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :colour="showAddTask ? 'red' : 'green'"
    />
  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  //   props: ["title"],
  props: {
    showAddTask: Boolean,
    // title: {
    //   type: String,
    //   default: "Hello World",
    // },
    title: String,
  },
  components: {
    Button,
  },
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
  },
  emits: ["btn-click"],
  // setup() {

  // },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
