<template>
  <div :key="task.id" v-for="task in tasks">
    <h3><Task @delete-task="$emit('delete-task', task.id)" :task="task" /></h3>
  </div>
</template>

<script>
import Task from "./Task";

export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ["delete-task"],
};
</script>