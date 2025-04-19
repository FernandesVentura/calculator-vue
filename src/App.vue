<script setup>
import { ref, computed } from 'vue'
import Title from './components/Title.vue'
import Content from './components/Content.vue'
import Result from './components/Result.vue'

  const num1 = ref(0)
  const num2 = ref(0)
  const operacao = ref('adicao')

  const resultado = computed(() => {
    switch (operacao.value) {
      case 'adicao':
        return num1.value + num2.value
      case 'subtracao':
        return num1.value - num2.value
      case 'multiplicacao':
        return num1.value * num2.value
      case 'divisao':
        return num2.value !== 0 ? (num1.value / num2.value).toFixed(2) : 'Erro: divisão por zero'
      default:
        return 0
    }
  })
</script>

<template>
  <div style="max-width: 300px;" class="container mt-5">
    <div style="max-width: 300px;" class="container mt-5">
    <Title />
    <Content v-model:num1="num1" v-model:num2="num2" v-model:operacao="operacao" />
    <Result :resultado="resultado" />
  </div>
    
  </div>
</template>

<style scoped>

h1 {
  text-align: center;
}
</style>
