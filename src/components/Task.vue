<template>
<div @dblclick="$emit('toggle-Reminder', task.id)" :class="[task.reminder?'reminder':'','task']">
    <h3>{{task.text}} 
    <i  @click="$emit('deleteTask', task.id)" class="fas fa-times"></i>

    </h3>
    <p>{{task.day}}</p>
    </div>
</template>
<script>
export default{
    name:'Task',
    props:{
        task:Object,
    },
    methods:{
        deleteTask(id){
            alert(id)
        }
    }
}
</script>
<style scoped>
.fas{
    color:red;
    cursor:pointer;
}
.task{
    margin:auto;
     background-color:rgb(184, 184, 179);
    margin-bottom:0.3rem;
    padding:0.5rem;
    width: 70%;
    cursor:pointer;


}
.fas{
    position :absolute;
    right:0;

}
.reminder{
    border-left: 0.5rem solid green;
}
</style>
