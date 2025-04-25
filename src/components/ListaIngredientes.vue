<template>
  <h4>{{ titulo }}</h4>
  <ul v-for="i in ingredientes" v-bind:key="i">
    <li v-if="i.length > 1">{{ i }}</li>
  </ul>
</template>
<script>
export default {
  name: 'ListaIngredientes',
  props: {
    ingredientes: Array,
    titulo: String,
  },
}
</script>
