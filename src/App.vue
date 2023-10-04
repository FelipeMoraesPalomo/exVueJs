<script setup>

import {reactive} from 'vue';


const estado = reactive({
  n1: Number,
  n2: Number,
  res: Number,
}
)

function calcula(){
  let select = document.getElementById('options').value

  switch (select){
    case "1":
      estado.res = estado.n1 + estado.n2;
      break;
    case "2":
      estado.res = estado.n1 - estado.n2;
      break;
    case '3':
      estado.res = estado.n1 * estado.n2;
      break;
    case '4':
      estado.res = estado.n1 / estado.n2;
      break;
  }
}

</script>

<template>
  <div class="container bg-primary d-flex vh-100">

    <form class="mx-auto my-auto bg-secondary w-50 h-50">

      <div class="row my-2 mx-2">

        <div class="col">
          <label for="number1" class="form-label">Primeiro número</label>
          <input required type="number" placeholder="Digite um número aqui"
          class="form-control" id="number1" v-on:change="calcula()"  v-model="estado.n1">
        </div>

        <div class="col">
          <label for="number2" class="form-label">Segundo número</label>
          <input required type="number" placeholder="Digite outro número aqui"
          class="form-control" id="number2" v-on:change="calcula()"  v-model="estado.n2" >
        </div>

      </div>

      <div class="row d-flex justify-content-center ">
        
        <div class="text-center w-25 mt-4">
          <input type="number" id="input"  class="form-control text-center" readonly placeholder="0" v-model="estado.res" >
        </div>
      </div>

      <div class="row  w-75 mx-auto mt-4">
        <select name="options" required id="options" v-on:change="calcula()" class="form-select text-center">

          <option selected value="1">Adição</option>
          <option value="2">Subtração</option>
          <option value="3">Multiplicação</option>
          <option value="4">Divisão</option>

        </select>
      </div>

    </form>
    
  </div>
</template>

<style scoped>

</style>
