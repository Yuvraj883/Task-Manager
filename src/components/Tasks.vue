<template>
    <div  :key="task.id" v-for="task in tasks">
       <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @deleteTask="$emit('deleteTask', task.id)" :task="task"/>
        </div>
</template>
<script>
import Task from './Task'
export default{
    name:'Tasks',
    props:{
        tasks:{
            type:Array,
        }
    },
    components :{
        Task
    }
}
</script>
<style  scoped>

</style>