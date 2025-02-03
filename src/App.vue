<script setup lang="ts">
import { ref } from 'vue';
import CalculoForm from './components/CalculoForm.vue';
import Resultado from './components/resultado.vue';  

const numero1 = ref<number | null>(null);
const numero2 = ref<number | null>(null);
const operador = ref<string>("+");
const resultado = ref<number | string>("");

function soma(numero1: number, numero2: number): number {
    return numero1 + numero2;
}

function subtracao(numero1: number, numero2: number): number {
    return numero1 - numero2;
}

function multiplicacao(numero1: number, numero2: number): number {
    return numero1 * numero2;
}

function divisao(numero1: number, numero2: number): number {
    return numero1 / numero2;
}

function calcular() {
    if (numero1.value !== null && numero2.value !== null) {
        switch (operador.value) {
            case "+":
                resultado.value = soma(numero1.value, numero2.value);
                break;
            case "-":
                resultado.value = subtracao(numero1.value, numero2.value);
                break;
            case "*":
                resultado.value = multiplicacao(numero1.value, numero2.value);
                break;
            case "/":
                if (numero2.value === 0) {
                    resultado.value = "Não é possível dividir por 0";
                } else {
                    resultado.value = divisao(numero1.value, numero2.value);
                }
                break;
            default:
                resultado.value = "Operação inválida";
        }
    } else {
        resultado.value = "Por favor, insira ambos os números";
    }
}

function updateInputs(data: { num1: number | null; num2: number | null; operator: string }) {
    numero1.value = data.num1;
    numero2.value = data.num2;
    operador.value = data.operator;
    calcular(); 
}
</script>

<template>
    <div class="container">
        <div class="container2">
            <header>
                <h1>Calculadora</h1>
            </header>
            <CalculoForm @updateInputs="updateInputs" />
            <Resultado :resultado="resultado" />
        </div>
    </div>
</template>

<style lang="scss">

$imagemFundo: "https://cdn.pixabay.com/photo/2021/10/05/21/46/math-6683827_1280.png";
$CorLetras: white;

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.container {
    display: grid;
    place-items: center;
    height: 100vh;
    max-width: 100%;
    background-image: url($imagemFundo);
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    background-color: rgb(4, 4, 4);
    
    .container2 {
        display: flex;
        flex-direction: column;
        justify-content: center;   
        align-items: center;       
        width: 40%;                
        height: auto;              
        background-color: rgba(0,0,0,0.9);
        border: 2px solid $CorLetras;
        border-radius: 20px;
        padding: 30px;             
        box-sizing: border-box;

        header {
            margin-bottom: 20px;
            text-align: center;
            color: $CorLetras;
            font-size: 25px;
        }
    
        .numeros {
            text-align: center;
            width: 100%; 
            max-width: 350px; 
            padding: 10px;
            margin-top: 10px;
            border-radius: 10px;
            box-sizing: border-box;
            margin-left: 80px;
            font-size: medium;
        }
        select {
            text-align: center;
            width: 100%; 
            max-width: 350px; 
            padding: 10px;
            margin-top: 10px;
            box-sizing: border-box;
        }

        .resultados{
            display: block;
            max-width: 100%;
            height: 30vh;
            text-align: center;
            justify-content: center;
            align-items: center;
            color: $CorLetras;
            margin-top: 20px;
            font-size: 25px;

            span{
                margin-left: auto;
                font-size: 40px;
            }
        }
    }
}

</style>
