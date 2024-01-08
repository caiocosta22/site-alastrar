<script setup>
</script>

<template lang="pug">
div.container
  q-parallax(
    height="1080"
    speed="1"
    src="/images/banner.jpg"
  )
    div.column(
      style="width:90%"
    )
      h1(
      ) Promova,
      h1(
      ) Propague
      h1(
      ) Espalhe
      q-btn(
        style="width:80px; border-radius: 20px; margin-top:10px"
        color="secondary"
      )
        p(
          style="margin:0"
          color="white"
        ) Botão
</template>

<style scoped>
.container{
  margin: 0 auto;
  display: flex;
  width: 100%;
  z-index: 1;
}
h1{
  color:#121212;
  font-weight: 600;
  text-align: left;
  margin: 0;
  font-size: 90px
}
</style>
