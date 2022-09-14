<template>
  <header>
    <h1>{{ title }}</h1>
    <Button text="Add Task" colour="green" />
  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  //   props: ["title"],
  props: {
    // title: {
    //   type: String,
    //   default: "Hello World",
    // },
    title: String,
  },
  components: {
    Button,
  },
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
