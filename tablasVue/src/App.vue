<script setup>
import { ref } from 'vue';
  let Entrada = ref()
  let constante = ref([])
  let result = ref([])
  
function subir(){
  constante.value.push(Entrada.value);
}

function multip(){
  for(let sumador = 1; sumador<=10;  sumador+=1 ){
    let sub = constante.value * sumador;
    result.value.push(sub);
  }   
}

</script>

<template>
  <div class="Entrada">
    <input @keypress.enter="subir" v-model="Entrada" type="number" placeholder=" ingresa un numero y presiona enter" >
    <button @click="multip" class="button">Add</button>
  </div>

  <div class="container" v-for="i in 10" :key="i">
    <div v-for="(constt, index) in constante" :key="index">{{ constt }}</div>
    <div>x</div>
    <div>{{ i }}</div>
    <div>=</div>
    <div>{{result[i-1]}}</div>
  </div>

</template>

<style scoped>

.container{
  display: flex;
  justify-content: center;
  margin-top: 40px;
  
}

.container > div{
  margin-left: 10px;
  
}

.Entrada{
  display: flex;
  justify-content: center;
  align-items: center;
}

input{
  display: flex;
  justify-content: center;
  margin-top: 30px;
  height: 20px;
  width: 250px;
  border-radius: 10px;
  text-decoration: none;
  background-color: rgb(255, 255, 255);
}

.button{
  margin-top: 20px;
  background-color: rgb(0, 0, 0);
  text-decoration: none;
  border-radius: 10px;
  height: 20px;
  color: white;
}

</style>
