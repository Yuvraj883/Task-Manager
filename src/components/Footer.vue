<template>
<footer>
   <router-link v-show="homePage" to="/about">User Guide</router-link>
   <p> Copyright &copy; 2022</p>

</footer>
</template>
<script>
export default{
    name:'Footer',
     computed:{
    homePage(){
            if(this.$route.path==="/"){
            return true
        }
        else{
            return false
        }
     }
 }
}
</script>
<style scoped>
footer{
margin-top:1.5rem;

}
</style>