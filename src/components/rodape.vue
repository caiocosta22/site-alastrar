<script setup>
</script>

<template lang="pug">
div.container
  div.interno
    div.logo
      q-img(
        src="/images/logo-branca.png"
      )
</template>

<style scoped>
.container {
  display: flex;
  background-color: #4b2059;
}
.interno {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 90%;
}
</style>
