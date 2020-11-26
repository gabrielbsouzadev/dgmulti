<template>
  <div class="container">
    <h1>Clientes</h1>
    <div class="row">
      <Cliente v-for="cliente in clientes" :key="cliente.numero" :cliente="cliente" />
    </div>
  </div>
</template>

<script>
import Cliente from "@/components/Cliente.vue";

export default {
  components: {
    Cliente
  },
  data() {
    return {
      clientes: []
    };
  },
  mounted() {
    this.$http
      .get("clientes")
      .then(response => (this.clientes = response.data))
      .catch(erro => console.log(erro));
  }
};
</script>

<style>
</style>