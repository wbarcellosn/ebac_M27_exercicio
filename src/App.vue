<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue';
  import Operacao from './components/Operacao.vue';
  import Resultado from './components/Resultado.vue';

  const estado = reactive({
    num1: '',
    num2: '',
    operacao: 'selecione',
    resultado: 0,
  });

  function calcularResultado() {
    switch (estado.operacao) {
      case 'adicao':
        if(estado.num1 && estado.num2 != ''){
          estado.resultado = parseFloat(estado.num1) + parseFloat(estado.num2);
          break;          
        }        
        else {
          estado.resultado = 0;
        }

      case 'subtracao':
        if(estado.num1 && estado.num2 != ''){
          estado.resultado = parseFloat(estado.num1) - parseFloat(estado.num2);
          break;          
        }        
        else {
          estado.resultado = 0;
        }

      case 'multiplicacao':
        if(estado.num1 && estado.num2 != ''){
          estado.resultado = parseFloat(estado.num1) * parseFloat(estado.num2);
          break;          
        }        
        else {
          estado.resultado = 0;
        }

      case 'divisao':
        if(estado.num1 && estado.num2 != ''){
          estado.resultado = parseFloat(estado.num1) / parseFloat(estado.num2);
          break;          
        }        
        else {
          estado.resultado = 0;
        }

      default:
        estado.resultado = 0;
    }
  }

</script>

<template>
  <div class="container col-4">
    
    <Cabecalho />
    <Operacao 
      :calcular-resultado="calcularResultado"
      :estado="estado"
    />
    <Resultado 
      :estado="estado"
    />
    
    
  </div>
</template>

<style scoped>

</style>
