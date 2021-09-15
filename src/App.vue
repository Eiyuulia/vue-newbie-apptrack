<template>
  <div id="todo">
    <div id="todo-header">
      <h1>To-Do</h1>
      <div id="add-task">Add Task</div>
    </div>
    <div id="todo-body">
      <div id="lists">
        <div class="list" v-for="task in tasks" :key="task.id">
          {{ task }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Task from "./components/Task";

export default {
  name: "App",
  components: { Task },
  data() {
    return {
      tasks: [],
    };
  },
  created() {
    this.tasks = [
      {
        id: 1,
        task: "writing essay",
        day: "selasa, 2 agustus at 02:00pm",
        remainder: true,
      },
      {
        id: 2,
        task: "writing essay",
        day: "selasa, 2 agustus at 02:00pm",
        remainder: true,
      },
      {
        id: 3,
        task: "writing essay",
        day: "selasa, 2 agustus at 02:00pm",
        remainder: false,
      },
    ];
  },
};
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  padding-top: 100px;
}
#todo {
  width: 50%;
  background-color: teal;
}

#todo-header {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100px;
}
#add-task {
  position: absolute;
  bottom: 0;
  right: 0;
  margin: 0 20px 20px 0;
  background-color: white;
}

#todo-body {
  background-color: yellowgreen;
  height: 500px;
}

#lists {
  background-color: wheat;
  width: 70%;
  height: 100%;
  margin: 0 auto;
  padding: 20px 0;
}
</style>
