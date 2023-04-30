<template>
  <div id="app">
    <TodoHeader></TodoHeader>
    <TodoInput v-on:add="addTask"></TodoInput>
    <TodoTask v-bind:propsdata="todoTasks" v-on:remove="removeTask"></TodoTask>
    <TodoFooter v-on:removeAll="clearAll" ></TodoFooter>
   
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoTask from './components/TodoTask.vue'
import TodoFooter from './components/TodoFooter.vue'

export default {
  name: 'App',
  data(){
    return{
      todoTasks:[]
    }
  },
  methods:{

    addTask(todoTask){
      localStorage.setItem(todoTask,todoTask);
      this.todoTasks.push(todoTask);
    },
    removeTask:function(todoTask,index){
      localStorage.removeItem(todoTask);
      this.todoTasks.splice(index,1); //해당 인덱스만 삭제
    },
    clearAll(){
      //전제 삭제, 화면에 보이는 목록들도 다 삭제
      localStorage.clear();
      this.todoTasks=[];
    }
  },
  components: {
    TodoHeader,TodoInput,TodoTask,TodoFooter
  }
}
</script>

<style>
  body{
    text-align: center;
    background-color: beige;
    
  }
 
</style>
