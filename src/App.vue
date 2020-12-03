<template>
  <div id="app">
    <Kanban :data="data" :create_task_submit="create_task_submit"/>
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
    return {
      data:[
        {
          name:"todo",
          color:"#D0B3E1",
          tasks:[
            {
              task_name:"test"
            }
          ]
        },
         {
          name:"doing",
          color:"#FDB4BF",
          tasks:[]
        },
         {
          name:"done",
          color:"#B9E3AE",
          tasks:[]
        }
      ]
    }
  },
  methods:{
    create_task_submit(column_index,item){
      this.data[column_index].tasks.push(item)
    }
  }
}
</script>

<style>
  #app {
  height: 100vh;
  }
</style>