<!--할 일 추가하는 컴포넌트-->
<!--  1. 버튼 클릭, 키보드 이벤트 핸들링 이용하기 ex>keypress,keyup -->
<!--  2. 입력값을 저장하고 다시 공백으로 바꿔놓기  -->
<template>
  <div>
      <!--키보드 이벤트 핸들링: 엔터 눌러도 계속 add 가능-->
      <!--input과 button 둘다 add 실행-->
    <input type="text" class="task_input" v-model="newTask" v-on:keyup.enter="add" placeholder="할일을 입력해주세요">
    <button class="addbtn" v-on:click="add">+</button>
  
  </div>
</template>

<script>
export default {
  data(){
    return{
      newTask:"",
    }
  },
  methods:{
    add:function(){
    
      //입력값이 있을때,없을때를 확인해서 따로 처리를 해줘야할듯???
      if(this.newTask !==''){
        //콘솔로 확인
        console.log(this.newTask);
        //로컬 스트리지에 입력한 값 저장하기
      //localStorage.setItem(this.newTask,this.newTask);
        // localStorage.setItem(value,value); -> App.vue에 있으닉까! 주석처리
        this.$emit('add',this.newTask);
        //입력값 비우기
        //this.newTask="";
        this.clear();
      }
    },
    clear:function(){
      this.newTask=""
    }
  }
}
</script>

<style>
  body{
    text-align:center;
  }
  input{
    width:400px;
    font-size:15px;
    border-radius:10px;
    
  }
  .task_input{
    width:400px;
    font-size:20px;
  }
  .addbtn{
 
    background: lightblue;
    margin-left:10px;
    font-size:15px;
    width:40px;
    height:30px;
    border-radius:5px;

    
    
  }
  .addbtn:hover{
    background: navy;
    color:white;
  }
</style>