<script setup>
const props = defineProps(['mudaNumero1','mudaSimbolo', 'mudaNumero2', 'resultadoOperacoes'])
</script>
<template>
    <div class="row">
        <div class="mb-4 col-12 d-flex justify-content-center border-bottom ">
            <h3>Faça as operações</h3>
        </div>
    </div>
    <div class="mb-4 row justify-content-center">
        <div class="col-4 ">
            <input @keyup="props.mudaNumero1" type="number" class="form-control ">
        </div>
        <span class="d-flex justify-content-center">{{ props.mudaSimbolo }}</span>
        <div class="col-4">
            <input @keyup="props.mudaNumero2" type="number" class="form-control">
        </div>
        <span class="mt-2 d-flex justify-content-center">{{ props.resultadoOperacoes }}</span>
    </div>
</template>

<style scoped>
input[type="number"]::-webkit-outer-spin-button,
input[type="number"]::-webkit-inner-spin-button {
    -webkit-appearance: none;

}
</style>