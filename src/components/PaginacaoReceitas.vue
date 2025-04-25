<template>
  <CardReceita v-for="receita in arrPagina" v-bind:key="receita.id" :receita="receita" />
  <br />
  <button @click="retornar()" v-show="pag > 1"><-</button> {{ pag }}
  <button @click="avancar()">-></button>
</template>
<script>
import CardReceita from './CardReceita.vue'
export default {
  name: 'PaginacaoReceitas',
  components: {
    CardReceita,
  },
  props: {
    receitas: Array,
  },
  data() {
    return {
      arrPagina: [],
      pag: 1,
    }
  },
  created() {
    this.paginar()
  },
  methods: {
    avancar() {
      this.pag++
      this.paginar()
    },
    retornar() {
      this.pag--
      this.paginar()
    },

    paginar() {
      this.arrPagina = this.receitas.slice(this.pag * 2 - 2, this.pag * 2)
    },
  },
}
</script>
<style></style>
