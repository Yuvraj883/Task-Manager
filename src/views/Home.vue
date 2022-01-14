<template>
     <div v-if="showAddTask">
      <AddTask v-show="showAddTask" @add-task="addTask" />
    </div>
    <Tasks
      @toggle-reminder="toggleReminder"
      @deleteTask="deleteTask"
      :tasks="tasks"
    />


</template>
<script>
import Tasks from "../components/Tasks";
import AddTask from "../components/AddTask";
export default{
    components:{
        Tasks,
        AddTask
    },
    data(){
        return {
      tasks: [],

        }
    },
    props:{
        showAddTask:Boolean
    },
    methods:{

   
    addTask(newTask) {
      //alert(newTask)
      //console.log(newTask)
      this.tasks = [newTask,...this.tasks];
      localStorage.setItem("Task-tracker-tasks", JSON.stringify(this.tasks));
    },
    deleteTask(id) {
      if (confirm("Are you sure? ")) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
        localStorage.setItem("Task-tracker-tasks", JSON.stringify(this.tasks));
      }
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
  },
computed:{
  reversedArr() {
      return this.items.slice().reverse()
    }
},

  mounted() {
    this.tasks = JSON.parse(localStorage.getItem("Task-tracker-tasks"))
      ? JSON.parse(localStorage.getItem("Task-tracker-tasks"))
      : [];
  },
    
}
</script>