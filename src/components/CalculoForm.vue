<script setup lang="ts">
import { ref, defineEmits } from 'vue';

const emit = defineEmits<{
    (event: 'updateInputs', value: { num1: number | null; num2: number | null; operator: string }): void;
}>();

const numero1 = ref<number | null>(null);
const numero2 = ref<number | null>(null);
const operador = ref<string>("+");


function atualizarInputs() {
    emit('updateInputs', {
        num1: numero1.value,
        num2: numero2.value,
        operator: operador.value
    });
}
</script>

<template>
    <div class="form-container">
        <input v-model.number="numero1" class="numeros" type="number" placeholder="Escolha um número"
            @input="atualizarInputs" />
        <select v-model="operador" class="numeros" @change="atualizarInputs">
            <option value="+">Soma</option>
            <option value="-">Subtração</option>
            <option value="*">Multiplicação</option>
            <option value="/">Divisão</option>
        </select>
        <input v-model.number="numero2" class="numeros" type="number" placeholder="Escolha outro número"
            @input="atualizarInputs" />
    </div>
</template>

<style scoped>

</style>
