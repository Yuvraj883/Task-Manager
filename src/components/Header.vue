<template>
    <h1>{{msg}}</h1>
    <Button button="Button"/>

</template>
<script>

import Button from './Button.vue'
export default{        
    name: 'Header',
    props:{
        msg:{
            type:String,
            default: 'Task Tracker'
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
