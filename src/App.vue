<script setup>
  import { reactive } from 'vue';

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
    <header class="p-5 mb-4 mt-4 bg-light rounded-3"> <!-- bg-light backgrond e rounded-3 para arredondar a borda -->
      <h1 class="">Calculadora aritmética</h1>
      <p class="fs-3">Resultado da Operação = <span class="badge bg-secondary fs-3">{{ estado.resultado  }}</span></p>
    </header>
    <form class="form-floating" @submit.prevent="getResultadoCalculado">
      <div class="row">
        <div class="col-md-4">
          <input class="form-control" type="number" @change="evento => estado.numero01 = evento.target.value" @blur="getResultadoCalculado" required placeholder="Digite aqui o primeiro valor">
        </div>
        <div class="col-md-4">
          <input class="form-control" type="number" @change="evento => estado.numero02 = evento.target.value" @blur="getResultadoCalculado" required placeholder="Digite aqui o segundo valor">
        </div>
        
        <div class="col-md-2">
          <select @change="evento => estado.operacao = evento.target.value" @blur="getResultadoCalculado" class="form-select">
            <option value="somar">Somar</option>
            <option value="diminuir">Diminuir</option>
            <option value="multiplicar">Multiplicar</option>
            <option value="dividir">Dividir</option>
          </select>
        </div>
        <div class="col-md-2">
            <button type="submit" class="btn btn-secondary" disabled>Calcular</button>
        </div>
      </div>  
    </form>
  </div>
</template>

<style scoped>
</style>
