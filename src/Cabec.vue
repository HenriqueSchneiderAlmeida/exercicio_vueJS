<script setup>
    const props = defineProps(['getResultadoCalculado'])
</script>
<template>
<header class="p-5 mb-4 mt-4 bg-light rounded-3">
    <h1 class="">Calculadora aritmética</h1>
    <p class="fs-3">Resultado da Operação = <span class="badge bg-secondary fs-3">{{ props.getResultadoCalculado }}</span></p>
</header>
</template>