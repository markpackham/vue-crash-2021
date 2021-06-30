<template>
  <div :key="task.id" v-for="task in tasks">
    <h3>
      <Task
        @toggle-reminder="$emit('toggleReminder', task.id)"
        @delete-task="$emit('deleteTask', task.id)"
        :task="task"
      />
    </h3>
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
  emits: ["toggle-reminder", "delete-task"],
};
</script>