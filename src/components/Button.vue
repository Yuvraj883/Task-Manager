<template>
    <button @click="onClick()" :style="{ background : color}">{{text}}</button>
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
        },
        

    },
    methods:{
        onClick(){
            this.$emit('btn-clicked')
        }
    }
}
</script>
<style scoped>
button{
    background: white;
    border-radius: .2rem;
    border-color: black;
    color:#fff;
    height:1.5rem;

}
</style>