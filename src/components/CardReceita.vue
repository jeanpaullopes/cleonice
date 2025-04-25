<template>
  <h2>{{ receita.receita }}</h2>
  <ListaIngredientes titulo="Ingredientes" :ingredientes="receita.ingredientes.split(',')" />

  <ListaIngredientes titulo="Modo de Preparo" :ingredientes="receita.modo_preparo.split('. ')" />
</template>
<script>
import ListaIngredientes from './ListaIngredientes.vue'
export default {
  name: 'CardReceita',
  components: {
    ListaIngredientes,
  },
  props: {
    receita: Object,
  },
}
</script>
<style></style>
