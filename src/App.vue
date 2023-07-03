<script setup>
  import { reactive } from 'vue';
  import Cabec from './Cabec.vue';
  import Formulario from './Formulario.vue';

  const estado = reactive ({
    operacao: 'somar',
    numero01: 0,
    numero02: 0,
    resultado:'',
  })
  
  const getResultadoCalculado = () => {
  const { operacao } = estado;
  
  switch (operacao) {
    case 'somar':
      return getSomar();
    case 'diminuir':
      return getDiminuir();
    case 'multiplicar':
      return getMultiplicar();
    case 'dividir':
      return getDividir();
    default: 
      return estado.operacao;
  } 
}

const getSomar = () => {    
    return estado.resultado = parseInt(estado.numero01) + parseInt(estado.numero02) } 
const getDiminuir = () => {    
    return estado.resultado = parseInt(estado.numero01) - parseInt(estado.numero02) } 
const getMultiplicar = () => {    
    return estado.resultado = parseInt(estado.numero01) * parseInt(estado.numero02) } 
const getDividir = () => {    
    return estado.resultado = parseInt(estado.numero01) / parseInt(estado.numero02) } 


</script>
 
<template>
  <div class="conteiner m-5">
    <Cabec :get-resultado-calculado="getResultadoCalculado()"></Cabec>
    <Formulario :get-resultado-calculado="getResultadoCalculado()" :capta-numero01="evento => estado.numero01 = evento.target.value" :capta-numero02="evento => estado.numero02 = evento.target.value" :capta-operacao="evento => estado.operacao = evento.target.value" ></Formulario>
  </div>
</template>

<style scoped>
</style>
