<script setup>
</script>

<template lang="pug">
div.container
  div.fotos
    div.interativa
      img(
        src="/images/teste/1.png"
      )
      div.overlay
        div.overlay2
          div.text Teste
    div.interativa
      img(
        src="/images/teste/2.png"
      )
      div.overlay
        div.overlay2
          div.text Teste
    div.interativa
      img(
        src="/images/teste/3.png"
      )
      div.overlay
        div.overlay2
          div.text Teste
    div.interativa
      img(
        src="/images/teste/4.png"
      )
      div.overlay
        div.overlay2
          div.text Teste
    div.interativa
      img(
        src="/images/teste/1.png"
      )
      div.overlay
        div.overlay2
          div.text Teste
    div.interativa
      img(
        src="/images/teste/2.png"
      )
      div.overlay
        div.overlay2
          div.text Teste
    div.interativa
      img(
        src="/images/teste/3.png"
      )
      div.overlay
        div.overlay2
          div.text Teste
    div.interativa
      img(
        src="/images/teste/4.png"
      )
      div.overlay
        div.overlay2
          div.text Teste
</template>

<style scoped>
.container {
  display: flex;
  margin: 0 auto;
  align-items: center;
  justify-content: center;
  flex-direction: column;
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
.fotos {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  max-width: 100%;
}
.interativa {
  position: relative;
  cursor: pointer;
}
img {
  max-width: 100%;
  display: block;
  height: auto;
  cursor: pointer;
}
.overlay {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 100%;
  width: 100%;
  opacity: 0;
  transition: 0.5s ease;
  background-color: #fff;
  z-index: 1;
}
.overlay2 {
  margin: auto;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 90%;
  width: 90%;
  opacity: 0;
  transition: 0.5s ease;
  background-color: #9A9A9A;
  z-index: 2;
}
.interativa:hover .overlay {
  opacity: 0.8;
}
.interativa:hover .overlay .overlay2 {
  opacity: 1;
}
.text {
  color: #FFF;
  font-weight: bold;
  font-size: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: center;
  z-index: 4;
  opacity: 1;
}
</style>
