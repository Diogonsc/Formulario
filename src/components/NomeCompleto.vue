<template>
  <div>
    <Rotulo nome="Nome" >
					<input type="text" :value="value.nome" @input="alterarNome">
		</Rotulo>
		<Rotulo nome="SobreNome">
					<input type="text" :value="value.sobreNome" @input="alterarSobreNome">
		</Rotulo>
  </div>
</template>

<script>
import Rotulo from "./Rotulo.vue";
export default {
  props:{
    value: {
      type: Object,
      required: true,
    }
  },
  components: {Rotulo},
  methods: {
    alterarNome(event) {
      this.$emit('input', {nome: event.target.value, sobreNome: this.value.sobreNome})
    },
    alterarSobreNome(event) {
      this.$emit('input', {nome: this.value.nome, sobreNome: event.target.value})
    }
  }
};
</script>

<style>
</style>
