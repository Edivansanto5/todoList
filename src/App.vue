<template>
  <div>
     <todoList/> 
     <!-- <playGround/> -->
  </div>
</template>
<script>
import todoList from './components/todoList.vue'
// import playGround from './components/playGround.vue'

import '@fortawesome/fontawesome-free/css/all.css'
import '@fortawesome/fontawesome-free/js/all.js'

  export default{
    components:{
      todoList,
      // playGround
    }
  }
</script>