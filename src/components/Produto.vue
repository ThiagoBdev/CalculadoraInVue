<script setup lang="ts">
const props = defineProps({
    resultado: {
        type: [String, Number],
        required: true
    }
});
</script>

<template>
    <div class="resultados">
        <h3>Resultado:</h3>
        <span>{{ resultado }}</span>
    </div>
</template>

<style scoped>

</style>
