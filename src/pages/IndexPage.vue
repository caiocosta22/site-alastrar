<script setup>
import apresentacao from "src/components/apresentacao.vue";
import trabalhos from "src/components/trabalhos.vue";
import institucional from "src/components/institucional.vue";
import showcase from "src/components/showcase.vue";
import clientes from "src/components/clientes.vue";
</script>

<template lang="pug">
q-page-container
  apresentacao
  institucional
  trabalhos
  showcase
  clientes
</template>

<style scoped>
</style>
