<template>
  <div class="kanban">
    <div class="column" :style="{backgroundColor:column.colors}" v-for="(column,index) in data" :key="index">
        
        <div class="column-header">
            {{column.name}}
        </div>

        <div class="column-body">
            <div class="create-task" @click="create_task(index)">
              Create Task
            </div>
        </div>
  </div>
  <b-modal ref="create-task_modal" title="Create Task">
    <p class="my-4">Hello from modal!</p>
  </b-modal>
  </div>
</template>

<script>
export default {
  props: {
    data: Array,
  },
  methods:{
    create_task(index_column){
      console.log(index_column);
        this.$refs["create-task_modal"].show()
    }
  }
};
</script>

<style>
.kanban {
  height: 100%;
  width: 100%;
  background-color: #6699AA;
}
.column{
    height: 600px;
    width: 300px;
    border-radius: 20px;
    display: inline-block;
    margin: 25px;
    padding: 10px;
    padding: auto;
    -webkit-box-shadow: 10px 13px 5px 0px rgba(0,0,0,0.37);
    -moz-box-shadow: 10px 13px 5px 0px rgba(0,0,0,0.37);
    box-shadow: 10px 13px 5px 0px rgba(0,0,0,0.37);
}
.column-header{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50px;
    font-size: 32px;
    font-weight: bold;
    
}
.column-body{
    height: calc(100% - 55px);
    border-radius: 10px;
    padding: 5px;
    background-color: rgba(207, 207, 221, 0.479);
}
.create-task{
  width: 100%;
  height: auto;
  padding: 10px;
  border-right: 5px;
  cursor: pointer;
}
.create-task:hover{
  background-color: #6699AA
}
</style>