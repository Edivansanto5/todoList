<template>
  <div>
     <todoList/> 
  </div>
</template>
<script>
import todoList from './components/todoList.vue'
import '@fortawesome/fontawesome-free/css/all.css'
import '@fortawesome/fontawesome-free/js/all.js'

  export default{
    components:{
      todoList
    }
  }
</script>