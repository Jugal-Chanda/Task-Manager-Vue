<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
      @btn-click="$emit('toggle-add-task')"
      :color="addTask ? 'red' : 'green'"
      :text="addTask ? 'Close' : 'Add Task'"
    />
    <!-- <Button color="red" text="Add Task" />
    <Button color="yellow" text="Add Task" />
    <Button color="black" text="Add Task" /> -->
  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  //   props: ["title"],
  props: {
    // title: String,
    title: {
      type: String,
      default: "Hello World",
    },
    addTask: {
      type: Boolean,
    },
  },
  components: {
    Button,
  },
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      }
      return false;
    },
  },
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