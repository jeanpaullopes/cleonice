<template>
  <h1>Bem vindo ao Receitas da Cleonice</h1>
  <PaginacaoReceitas :receitas="receitasArray" />
</template>
<script>
import PaginacaoReceitas from '@/components/PaginacaoReceitas.vue'
export default {
  name: 'HomeView',
  components: {
    PaginacaoReceitas,
  },
  data() {
    return {
      receitasArray: Array,
    }
  },
  created() {
    fetch('https://api-receitas-pi.vercel.app/receitas/todas').then((response) => {
      if (!response.ok) {
        throw new Error('Network response was not ok')
      }
      response.json().then((data) => {
        this.receitasArray = data
      })
    })
  },
}
</script>
<style></style>
