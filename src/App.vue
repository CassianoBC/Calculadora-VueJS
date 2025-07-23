<script setup>
  
</script>

<template>
  <div class="container">
    <h1>Calculador Aritmédica</h1>
    <form>
        <input class="me-3" type="number" placeholder="Insira um número" />
        <select class="" name="" id="">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="/">/</option>
            <option value="*">*</option>
        </select>
        <input class="ms-3" type="number" placeholder="Insira um número" />
        <span class="me-3 ms-3">=</span>
        <span>
            resultado
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
    border-radius:15px 15px 0 0;
    width: 100%;
    color: #fff;
    background-color: oklch(64.5% 0.246 16.439);
}

form {
    padding: 30px;
    background-color: oklch(81% 0.117 11.638);
    width: 100%;
    border-radius: 0 0 15px 15px;
    display: flex;
    justify-content: center;
    align-items: center;
}

input {
    border: none;
    border-bottom: 3px solid #fff;
    background: transparent;;
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


</style>