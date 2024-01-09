<script setup>
</script>

<template lang="pug">
div.titulo
  h2 Captação de conteúdo audiovisual
div.container
  div.interno
    iframe(
        height="100%"
        width="100%"
        src="https://www.youtube.com/embed/dQw4w9WgXcQ"
        frameborder="0"
        allowfullscreen
      )
</template>

<style scoped>
.titulo {
  text-align: center;
}
.container {
  display: flex;
  margin: 40px auto;
  position: relative;
  width: 60%;
  background-color: #f1bc00;
  height: 500px;
  border-radius: 40px;
}
.interno {
  margin: 20px auto;
  width: 90%;
  border-radius: 40px;
}
</style>
