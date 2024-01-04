<script setup>
import cabecalho from "src/components/cabecalho.vue";
</script>

<template lang="pug">
q-layout(
    view="lHh Lpr lFf"
  )
  q-header
    cabecalho
  RouterView
</template>

<style scoped>
</style>
