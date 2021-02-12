<template>
  <div>
    <Rotulo nome="Nome">
      <input type="text" @input="alterarNome" :name="name.nome" />
    </Rotulo>
    <Rotulo nome="Sobrenome">
      <input type="text" @input="alterarSobrenome" :name="name.sobrenome" />
    </Rotulo>
  </div>
</template>

<script>
import Rotulo from "./Rotulo";
export default {
  props: {
    name: { type: Object, required: true },
  },
  components: { Rotulo },
  methods: {
    alterarNome(event) {
      this.$emit("input", {
        nome: event.target.value,
        sobrenome: this.value.sobrenome,
      });
    },
    alterarSobrenome(event) {
      this.$emit("input", {
        nome: this.value.nome,
        sobrenome: event.target.value,
      });
    },
  },
};
</script>
