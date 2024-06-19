<script setup>
import {reactive} from 'vue';

const estado = reactive({
  simbolo: '+',
  filtro: 'somar',
  numero1:0,
  numero2:0
})

const operacoes= () =>{
  const {filtro} = estado;
  let resultado = '';
  switch(filtro){
    case'somar':
    resultado = parseInt(estado.numero1) + parseInt(estado.numero2); 
    estado.simbolo = '+';
    return resultado
    case 'subt':
      resultado = estado.numero1 - estado.numero2
      estado.simbolo = '-'
      return resultado;
    case 'mult':
      resultado =estado.numero1 * estado.numero2
      estado.simbolo = '*'
      return resultado
    case 'dividir':
    resultado = estado.numero1 / estado.numero2
    estado.simbolo = '/'
    return resultado
}

}
console.log(operacoes())

</script>

<template>
<div class="col-md-4 container bg-light ">
<header class="pt-4 pb-4">
  <h1>Calculadora Aritimética</h1>
</header>


<div class="row">
  <div class="mb-4 col-12 d-flex justify-content-center border-bottom ">
    <h3>Faça as operações</h3>
  </div>
</div>
<div class="mb-4 row justify-content-center">
  <div class="col-4 ">
    <input @keyup="evento => estado.numero1 = evento.target.value" type="number" class="form-control ">
  </div>
  <span class="d-flex justify-content-center">{{ estado.simbolo }}</span>
  <div class="col-4">
    <input @keyup="evento => estado.numero2 = evento.target.value"  type="number" class="form-control">
  </div>
  <span class="mt-2 d-flex justify-content-center">{{ operacoes() }}</span>
</div>


<div class="row justify-content-center">
<div class="col-3 ">
  <select @change="evento => estado.filtro = evento.target.value" class="form-control wd-4">
    <option value="somar">Somar</option>
    <option value="subt">Subtrair</option>
    <option value="mult">Multiplicar</option>
    <option value="dividir">Dividir</option>
  </select>
</div>
</div>
</div>
</template>

<style scoped>
input[type="number"]::-webkit-outer-spin-button,
input[type="number"]::-webkit-inner-spin-button {
    -webkit-appearance: none;

}
</style>
