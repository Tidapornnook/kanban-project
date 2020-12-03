<template>
  <div id="app">
   <Kanban :data = "data"/>
  </div>
</template>

<script>
import Kanban from "./components/Kanban"


export default {
  name: 'App',
  components: {
   Kanban
  },
  data(){
    return{
      data:[
        {
          name:"todo",
          colors:"#CBAB8D",
          tasks:[]
        },
        {
          name:"doing",
          colors:"#B9E3AE",
          tasks:[]
        },
        {
          name:"done",
          colors:"#D0B3E1",
          tasks:[]
        }
      ]
    }
  }
}
</script>

<style>
#app {
  height:100vh ;
}
</style>