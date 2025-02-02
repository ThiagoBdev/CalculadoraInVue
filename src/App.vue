<script setup lang="ts">
    
</script>

<template>
<div class="container">
    <div class="container2">
        <header>
            <h1>Calculadora</h1>
        </header>
        <form>
            <input class="numeros" type="text" id="numero1" placeholder="Escolha um numero:">
            <select class="numeros">
                <option>Soma</option>
                <option>Subtração</option>
                <option>Multiplicação</option>
                <option>Divisão</option>
            </select>
            <input class="numeros" type="text" id="numero2" placeholder="Escolha outro numero numero:">
            <div class="resultados">
                <h3 class="numeros" id="Resultado">Resultado:</h3>
                <span class="numeros">{{2}}</span>
            </div>
        </form>
    </div>
</div>
</template>

<style lang="scss">
    $imagemFundo: "https://cdn.pixabay.com/photo/2021/10/05/21/46/math-6683827_1280.png";

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
        min-width: 300px;          
        height: auto;              
        background-color: rgba(0,0,0,0.9);
        border: 2px solid rgba(255,255,255, 0.7);
        border-radius: 20px;
        padding: 30px;             
        box-sizing: border-box;

        header {
            margin-bottom: 20px;
            text-align: center;
            color: white;
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
            color: aliceblue;
            margin-top: 20px;
            background-color: rgba(0,0,0,0.9);
            border: 2px solid rgba(255,255,255, 0.7);
            font-size: 25px;

            span{
                margin-left: auto;
                font-size: 40px;
            }
        }
    }
}


</style>
