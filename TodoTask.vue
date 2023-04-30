<template>
  <div >
  <ul>  
    <!--저장된 todoTask 개수만큼 Task 리스트인 todoTask가 생김.-->
      <li v-for="(todoTask,index) in propsdata" v-bind:key="todoTask">{{ todoTask }}  
      <button class="deletebtn" v-on:click="remove(todoTask,index)"> X </button>
    
  </li>
   </ul>
</div>
</template>

<script>
export default {
 
  props:['propsdata'],
  methods:{ //삭제 기능 메소드
    remove:function(todoTask,index){
      this.$emit("remove",todoTask,index);
    }
  },
  
  };
</script>


<style>
  ul{
    width:450px;
    padding-left:0;
    margin-top:10px;
    display:block;
    margin:0 auto;
}
 li {

  list-style-type: none;
  display:flex;
  justify-content: center;
  height: 50px;
  line-height: 50px;
  margin: 20px 0;
  padding: 0 5px;
  background: white;
  border-radius: 5px;
}
.deletebtn{
  margin-left:20px;
  height:30px;
  margin-top:10px;
  border-radius: 5px;
  color:red;
  background:white; 
}
.deletebtn:hover{
  color:black;
  background:lightblue;
}
</style>