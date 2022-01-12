<template>
<div @dblclick="$emit('toggle-Reminder', task.id)" :class="[task.reminder?'reminder':'','task']">
    <h3>{{task.text}} 
    <i  @click="$emit('deleteTask', task.id)" class="fa fa-times"></i>

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
.fa{
color:red;

right:0;
 

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
    margin-left:10rem;

}
.reminder{
    border-left: 0.5rem solid green;
}
</style>
<style scoped>
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.2/css/all.min.css");
</style>