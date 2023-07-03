<script setup>
    const props = defineProps(['getResultadoCalculado', 'captaNumero01', 'captaNumero02', 'captaOperacao'])
</script>
<template>
<form class="form-floating" @submit.prevent="props.getResultadoCalculado">
    <div class="row">
        <div class="col-md-4">
            <input class="form-control" type="number" @change="props.captaNumero01" @blur="props.getResultadoCalculado" required placeholder="Digite aqui o primeiro valor">
        </div>
        <div class="col-md-4">
            <input class="form-control" type="number" @change="props.captaNumero02" @blur="props.getResultadoCalculado" required placeholder="Digite aqui o segundo valor">
        </div>
        <div class="col-md-2">
            <select @change="props.captaOperacao" @blur="props.getResultadoCalculado" class="form-select">
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
</template>