<template>
<header>
    <h1>{{title}}</h1>
    <Button title= "Add task"/> 
    <AddNew />
</header>
 
</template>
<script>
import Button from './Button.vue'
import AddNew from '../components/AddTask.vue'
export default {
   name: 'Header',  
   components:{
       Button,
      
   },
   props: {
       title: {
           type: String,
       }
   }
}
</script>
<style scoped>
header {
    display:flex;
    justify-content: space-between;
    align-items:center;
    margin-bottom: 20px;
}
</style>