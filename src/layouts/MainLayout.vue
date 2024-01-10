<script setup>
import cabecalho from "src/components/cabecalho.vue";
import rodape from "src/components/rodape.vue";
</script>

<template lang="pug">
q-layout(
    view="lHh Lpr lFf"
  )
  q-header
    cabecalho
  RouterView
  rodape
</template>

<style scoped>
</style>
