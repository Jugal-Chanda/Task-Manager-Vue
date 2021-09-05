<template>
  <div :key="task.id" v-for="task in tasks">
    <Task
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      :task="task"
    />
  </div>
</template>
<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  components: {
    Task,
  },
  props: {
    tasks: {
      type: Array,
      default: [],
    },
  },
  methods: {},
  emits: ["delete-task", "toggle-reminder"],
};
</script>
