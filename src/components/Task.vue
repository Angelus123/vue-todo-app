<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : 'task']"
  >
    <h3>
      {{ task.text }}
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>
<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
};
</script>

<style scoped>
.fas {
  color: red;
  float: right;
  margin: 5px;
}
.task {
  width: 400px;
  padding: 10px 0;
  height: fit-content;
  border: 1px rgba(127, 128, 129, 0.904) solid;
  border-left: 5px solid rgba(38, 84, 105, 0.425);
  margin: 10px auto;
  align-items: center;
}
.reminder {
  width: 400px;
  padding: 10px 0;
  height: fit-content;
  border: 1px rgb(98, 99, 100) solid;
  border-left: 5px solid rgba(0, 128, 0, 0.363);
  margin: 10px auto;
  align-items: center;
}
.task:hover {
  width: 400px;
  height: fit-content;
  border: 1px rgb(122, 124, 126) solid;
  border-left: 5px solid rgba(38, 84, 105, 0.658);
  margin: 10px auto;
  transition: 0.8s all;
}
.reminder:hover {
  width: 400px;
  height: fit-content;
  border: 1px rgb(98, 99, 100) solid;
  border-left: 5px solid green;
  
  margin: 10px auto;
  transition: 0.8s all;
}


</style>