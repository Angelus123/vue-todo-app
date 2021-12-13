<template>
  <div class="container">
    <Header title = "Tasker Manager" /> 
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks='tasks'/>
    <router-view></router-view>
    <Footer />
  </div>
</template>


<script>
import Header from '../components/Header.vue'
import Tasks from '../components/Tasks.vue'
import Footer from '../components/Footer.vue'
export default {
  name: "App",
  components: {
    Header,
    Tasks,
    Footer,
  },
  data() {
    return {
      tasks: []
    }
  }, 
  methods: {
    deleteTask(id){
      if(confirm('Are you sure?'))
      this.tasks= this.tasks.filter((task) => task.id !== id)
      // this.tasks.splice(id,1)

    },
    toggleReminder(id){
        this.tasks =this.tasks.map((task) =>
        
        task.id === id ? { ...task, reminder: !task.reminder}:task)
    }

  },
  created() {
    this.tasks = [
      {
        id: 1,
        text:'Doctors Appointment',
        day:'March 1st at 2:30pm',
        reminder:false
      },
      {
        id: 2,
        text:'Meeting at School',
        day:'March 2nd at 2:30pm',
        reminder:true
      },
      {
        id: 3,
        text:'Food Shopping',
        day:'March 3rd  at 2:30pm',
        reminder:true
      }
    ]
  }  
};
</script>


<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
}
.container {
  width:70%;
  height: auto;
  margin:0 auto; 
  text-align: center;
  border: 1px solid steelblue;
  
}
h1{
  text-align: center;
  color:steelblue;
}

</style>
