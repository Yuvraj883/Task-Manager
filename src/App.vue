<template>
<div class="container">
  <Header @btn-clicked="toggleAddTask" msg="Task Tracker" :updateButton="showAddTask"/>
  <div v-if="showAddTask">
  <AddTask @add-task="addTask"/>
  </div>
  <Tasks @toggle-reminder="toggleReminder" @deleteTask="deleteTask" :tasks="tasks"/>

  </div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'


export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask
  }, 
  data(){
    return {
      tasks:[],
      showAddTask:false
    }
  },
  methods:{
    toggleAddTask(){
      this.showAddTask=!this.showAddTask
    },
    addTask(newTask){
      
      
      this.tasks= [...this.tasks, newTask]
      localStorage.setItem('Task-tracker-tasks',JSON.stringify(this.tasks))
      
    },
    deleteTask(id){
    if(confirm('Are you sure? ')){
      this.tasks = this.tasks.filter((task)=>task.id!==id)
       localStorage.setItem('Task-tracker-tasks',JSON.stringify(this.tasks))

    }

    },
    toggleReminder(id){
    this.tasks = this.tasks.map((task)=>task.id===id ? {...task,reminder:!task.reminder} :task)
    }

  },
 
  mounted(){
    
  this.tasks= JSON.parse(localStorage.getItem('Task-tracker-tasks')) ? JSON.parse(localStorage.getItem('Task-tracker-tasks')) : [];
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container{
  background-color:black;
  margin: 1rem auto;
  max-width:500px;
  min-width:300px;
  overflow:auto;
  padding : 1rem;
  width: 80%;
  border: 0.5rem solid;
  border-color: red;
  
}

</style>
