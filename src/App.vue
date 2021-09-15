<template>
  <div id="todo">
    <div id="todo-header">
      <h1>To-Do</h1>
      <div id="add-task" @click="addTask"><div>Add Task</div></div>
    </div>
    <div id="todo-body">
      <div id="lists">
        <Tasks :tasks="tasks" />
      </div>
    </div>
  </div>
</template>

<script>
import Tasks from "./components/Tasks";

export default {
  name: "App",
  components: { Tasks },
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
        task: "Math Assignment",
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
  methods: {
    addTask() {
      this.tasks.push({ id: 3, task: "tes", day: "tes", remainder: true });
    },
  },
};
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  padding-top: 100px;
  background-color: #3fb27f;
}
#todo {
  width: 50%;
  background-color: whitesmoke;
}

#todo-header {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100px;
}
#todo-header h1 {
  font-size: 3rem;
  color: #32475b;
}
#add-task {
  cursor: pointer;
}
#add-task div {
  position: absolute;
  bottom: 0;
  right: 0;
  margin: 0 20px 10px 0;
  padding: 5px;

  border-radius: 5px;
  background-color: #32475b;
  color: white;
}
#add-task:hover div {
  transform: translate(-3px, -3px);
  box-shadow: 3px 3px 3px black;
}

#todo-body {
  background-color: whitesmoke;
  min-height: 500px;
}

#lists {
  background-color: whitesmoke;
  width: 80%;
  min-height: 500px;
  margin: 0 auto;
  padding: 20px 0;
}
</style>
