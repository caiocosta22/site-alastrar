<script setup>
</script>

<template lang="pug">
div.container
  div.titulo
    h3 Nossos trabalhos
    div.menus
      p Todos
      p Captação
      p Fotografias
      p Sites
      p Campanhas de Tráfego
  div.fotos
</template>

<style scoped>
.container {
  display: flex;
  margin: 0 auto;
  align-items: center;
  justify-content: center;
}
.titulo {
  width: 60%;
  justify-content: space-between;
  align-items: center;
  flex-direction: row;
  display: flex;
}
.menus {
  display: flex;
  flex-direction: row;
  align-items: center;
}
.menus>p {
  padding-left: 30px;
  font-size: 18px;
  color: #a9a9a9;
  padding-top: 15px;
}
.menus>p:hover {
  color: rgba(0,0,0,1);
  transition: 0.5s;
  cursor: pointer;
  text-decoration: underline;
}
</style>
