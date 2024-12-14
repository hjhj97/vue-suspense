
<template>
  <div class="container">
    <ul>
      <li v-for="i in 3" :key="i" class="item"></li>
    </ul>
  </div>
</template>
<style scoped>
.container{
  padding : 10px;
  border-radius: 10px;
  width : 100%;
  background-color: #eaeaea;
}
ul{
  display: flex;
  flex-direction: column;
  gap : 16px;
}
li{
  width : 400px;
  height: 30px;
  background-color: #bcbcbc;
  border-radius: 8px;
  list-style-type: none;
  animation: pulse 2s infinite;
}

@keyframes pulse{
  0%{
    background-color: #ccc;
  }
  50%{
    background-color: #ddd;
  }
  100%{
    background-color: #ccc;
  }
}
</style>
