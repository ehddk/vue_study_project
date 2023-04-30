<template>
  
  <!-- <div class="all" v-on:click="clearTask">
    <span class="clear"><buttton>전체 삭제</buttton></span>
  </div> -->
  <div>
    <button class="clearAll" v-on:click="removeAll">전체 삭제</button>
  </div>
</template>

<script>

export default {
  methods:{
    removeAll:function(){
      // localStorage.clear();
      alert("정말 삭제하시겠습니까?")
      this.$emit('removeAll');
      
    }
  }
}
</script>

<style scoped>
  .clearAll {
  color: red;
  background:white;
  border-style:none;
  background:lightblue;
  padding:10px;
  border-radius:5px;
  margin-top:10px;
}
</style>