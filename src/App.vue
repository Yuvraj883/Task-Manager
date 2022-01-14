<template>
  <div class="container">
    <Header
      @btn-clicked="toggleAddTask"
      msg="Task Tracker"
      :updateButton="showAddTask"
    />
    <router-view v-show="homePage" :showAddTask="showAddTask"></router-view>
   
    <Footer/>
  </div>
</template>

<script>
import Header from "./components/Header";

import Footer from "./components/Footer"

export default {
  name: "App",
  components: {
    Footer,
    Header
    
      },
  data() {
    return {
      showAddTask:false,
    };
  },
 methods:{
 toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    },
 }

};
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
.container {
  background-color:black;
  margin: 1rem auto;
  max-width: 500px;
  min-width: 300px;
  overflow: auto;
  padding: 1rem;
  width: 80%;
  border: 0.5rem solid;
  border-color: red;
}
</style>
