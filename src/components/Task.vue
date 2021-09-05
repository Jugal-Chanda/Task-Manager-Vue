<template>
  <div
    @click="toggleReminder(task.id)"
    :class="[task.remider ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }}

      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>
<script>
// import { defineComponent } from '@vue/composition-api'

export default {
  name: "Task",
  props: {
    task: {
      type: Object,
    },
  },
  methods: {
    toggleReminder(id) {
      this.$emit("toggle-reminder", id);
    },
  },
};
</script>
<style scoped>
.fas {
  color: red;
}
div {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
