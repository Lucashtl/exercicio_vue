<script setup>
const props = defineProps(['mudaOperacao'])
</script>
<template>
    <div class="row justify-content-center">
        <div class="col-3 ">
            <select @change="props.mudaOperacao" class="form-control wd-4">
                <option value="somar">Somar</option>
                <option value="subt">Subtrair</option>
                <option value="mult">Multiplicar</option>
                <option value="dividir">Dividir</option>
            </select>
        </div>
    </div>
</template>