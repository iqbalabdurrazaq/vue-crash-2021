<template>
  <div :key="task_data.id" v-for="task_data in tasks">
    <Task
      @toggle-reminder="$emit('toggle-reminder', task_data.id)"
      @delete-task="$emit('delete-task', task_data.id)"
      :task_items="task_data"
    />
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  components: { Task },
  name: "Tasks",
  props: {
    tasks: Array,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>
