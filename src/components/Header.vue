<template>
    <h1>{{msg}}</h1>
    <Button 
    :text="updateButton?'Close':'Add Task'"
    :color="updateButton?'red':'green'"
    @btn-clicked="$emit('btn-clicked')" button="Button"/>

</template>
<script>

import Button from './Button.vue'
export default{        
    name: 'Header',
    props:{
        msg:{
            type:String,
            default: 'Task Tracker'
        },
        updateButton:{
            type:Boolean
        }
    },
    components: {
        Button,
    }
}
</script>
<style scoped>
h1{
    display:inline-flex;
    margin: 1rem;
    padding : 0.3rem;
}
</style>
