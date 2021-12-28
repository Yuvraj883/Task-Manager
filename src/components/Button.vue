<template>
    <button @click="onClick()" style="{background:color">{{text}}</button>
</template>
<script>
export default{
    name: 'Button',
    props:{
        text:{
            type:String,
            default: 'Add Task',
        },
        color:{
            type:String,
            
        }
    },
    methods:{
        onClick(){
            alert("button clicked");
        }
    }
}
</script>
<style scoped>
button{
    background-color: blue;
    border-radius: .2rem;
    border-color: red;
    color:white;
    height:1.5rem;

}
</style>