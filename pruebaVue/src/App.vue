<script setup>
  let saluda = "hello world";
</script>

<template>
  <h1>{{ saluda }}</h1>

  <div>
    <h2>-</h2>
    <h2>+</h2>
  </div>

</template>

<style scoped>

 h1{
  background-color: aqua;
  text-align: center;
 }
 div{ 
  display: flex;
  justify-content: center;
 }

 h2{
  background-color: blue;
  width: 30px;
  text-align: center;
  margin: 0px 10px;
 }

</style>
