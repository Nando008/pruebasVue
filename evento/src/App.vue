<script setup>
import { ref } from 'vue';

let Revent = ref('')
let Rname = ref('')
let Rapellido = ref('')


let edad = ref('')
let años = 0
let totalEdad = 0
let pasAño = 1000*60*60*24*365


function capEdad(){
  const timeActual = new Date()

  let timeAge = new Date(edad.value)

  totalEdad = timeActual-timeAge

  años = parseInt(totalEdad/pasAño)
  
  return años
}

let Rnum = ref('')


</script>

<template>
  <body class="container">

    <div class="entrada">
      
      <input v-model="Revent" type="text" placeholder="   Ingresa nombre del evento">
      
      <h1 class="h">Registrate</h1>
      
      <input v-model="Rname" type="text" placeholder="   Ingresa tu nombre">
      <input v-model="Rapellido" type="text" placeholder="   Ingresa tu apellido">
      <h4 class="h">Fecha de nacimiento</h4>
      <input type="date" v-model="edad"><button @click="capEdad">enviar edad</button>
      <input type="text" v-model="Rnum" placeholder="   Ingresa numero celular">
      
    </div>

    <div class="salida">
      <h1 class="hSalida" > {{ Revent }}</h1>
      <h4 class="hSalida">{{ Rname }} {{ Rapellido }}</h4>
      <h4 class="hSalida">{{ años }}</h4>
      <h4 class="hSalida">{{ Rnum }}</h4>
      <h4 class="hSalida" v-show="años < 18">Joven necesita un acompañante</h4>
    </div>

  </body>
</template>

<style scoped>

button{
  width: 20px;
  margin-left: 40%;
  width: 25%;
  font-family: Kdam Thmor Pro;
}

body{
  display: flex;
  justify-content: space-around;
  height: 500px;
  font-family: Kdam Thmor Pro;
  margin-top: 60px;
}

.h{
  text-align: center;
}
.entrada{
  background-color: blue;
  display: flex;
  flex-direction: column;
  width: 400px;
  padding-top: 40px;
  border: rgba(0, 0, 0, 0.591) solid;
}

input{
  margin-top: 10px;
  width: 50%;
  display: flex;
  justify-content: center;
  margin-left: 25%;
  margin-right: 25%;
  border-radius: 10PX;
  height: 25px;
  text-decoration: none;
  background-color: rgba(240, 255, 255, 0.745);
  border: rgb(0, 0, 0) solid;
  color: black;
  font-family: Kdam Thmor Pro;
}

.salida{
  background-color: brown;
  width: 400px;
  text-align: center;
  border: rgba(0, 0, 0, 0.591) solid;
}

.hSalida{
  margin-top: 50px;
}
</style>
