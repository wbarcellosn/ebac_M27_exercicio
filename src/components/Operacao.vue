<script setup>

const props = defineProps(['calcularResultado', 'estado']);

</script>

<template>
    <div class="row p-2 rounded-4 mt-3">
      <form class="mx-auto col-8 row ">
        <label for="num1" class="form-label text-center fw-bold">Digite o primeiro número</label>
        <input id="num1" type="number" class="form-control mb-3" v-model="props.estado.num1" @change="props.calcularResultado">

        <label for="num2" class="form-label text-center fw-bold">Digite o segundo número</label>
        <input id="num2" type="number" class="form-control mb-3" v-model="props.estado.num2" @change="props.calcularResultado">

        <label for="operator" class="form-label text-center fw-bold">Selecione a operação desejada</label>
        <select id="operator" class="form-control mb-3" v-model="props.estado.operacao" @change="props.calcularResultado">
          <option value="selecione" selected disabled>Selecione</option>
          <option value="adicao">Adição</option>
          <option value="subtracao">Subtração</option>
          <option value="multiplicacao">Multiplicação</option>
          <option value="divisao">Divisão</option>
        </select>

        <button type="submit" class="btn btn-danger">Zerar calculadora</button>
      </form>
    </div>
</template>