<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Inputs from './components/Inputs.vue';
import Selects from './components/Select.vue';


const estado = reactive({
  simbolo: '+',
  filtro: 'somar',
  numero1: 0,
  numero2: 0
})

const operacoes = () => {
  const { filtro } = estado;
  let resultado = '';
  switch (filtro) {
    case 'somar':
      resultado = parseInt(estado.numero1) + parseInt(estado.numero2);
      estado.simbolo = '+';
      return resultado
    case 'subt':
      resultado = estado.numero1 - estado.numero2
      estado.simbolo = '-'
      return resultado;
    case 'mult':
      resultado = estado.numero1 * estado.numero2
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
    <Cabecalho />
    <Inputs :muda-numero1="evento => estado.numero1 = evento.target.value" :muda-simbolo="estado.simbolo"
      :muda-numero2="evento => estado.numero2 = evento.target.value" :resultado-operacoes="operacoes()" />
    <Selects :muda-operacao="evento => estado.filtro = evento.target.value" />




      
  </div>
</template>
