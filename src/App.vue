<script setup>
    import { reactive } from 'vue';

    const numeros = reactive({
        numero1: 0,
        numero2: 0,
        operador: '+',
        resultado: 0
    })

    function calcular() {
        const n1 = parseFloat(numeros.numero1);
        const n2 = parseFloat(numeros.numero2);

        switch (numeros.operador) {
            case '+':
                numeros.resultado = n1 + n2;
                break;
            case '-':
                numeros.resultado = n1 - n2;
                break;
            case '*':
                numeros.resultado = n1 * n2;
                break;
            case '/':
                numeros.resultado = n2 !== 0 ? n1 / n2 : 'Erro: Divisão por zero';
                break;
            default:
                numeros.resultado = 'Operador inválido';
        }
    }
</script>

<template>
    <div class="container">
        <h1>Calculador Aritmédica</h1>
        <form>
            <input @keyup="evento => {numeros.numero1 = evento.target.value; calcular()}" class="me-sm-3" type="number" placeholder="Insira um número" />
            <select @change="evento => {numeros.operador = evento.target.value; calcular()}" class="" name="" id="">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="/">/</option>
                <option value="*">*</option>
            </select>
            <input @keyup="evento => {numeros.numero2 = evento.target.value; calcular()}" class="ms-sm-3" type="number" placeholder="Insira um número" />
            <span class="me-sm-3 ms-sm-3">=</span>
            <span>
                {{ numeros.resultado }}
            </span>
        </form>
    </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    margin-top: 250px;
    max-width: 760px;
    width: 100%;
}

h1 {
    margin: 0;
    padding: 20px;
    border-radius: 15px 15px 0 0;
    width: 100%;
    background-color: #ffefc1;
}

form {
    padding: 30px;
    background-color: #fb6066;
    color: #fff;
    width: 100%;
    border-radius: 0 0 15px 15px;
    display: flex;
    justify-content: center;
    align-items: center;
}

input {
    border: none;
    border-bottom: 3px solid #fff;
    background: transparent;
    color: #fff
    ;
}

input::placeholder {
    color: #fff;
}

select {
    border: none;
    border-bottom: 3px solid #fff;
    background: transparent;
    color: #fff;
}

@media (max-width: 575px) {
    form {
        flex-direction: column;
        align-items: center;
    }

    input, select {
        width: 100%;
        margin-bottom: 10px;;
        margin: 0;
    }
}
</style>