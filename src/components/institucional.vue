<script setup>
</script>

<template lang="pug">
div.container
  div.icones
    div(
      v-for="index in 6"
      :key="index"
    )
      q-icon(
        name="fa-solid fa-bug"
        color="info"
        size="xl"
      )
      p(style="font-size:24px;color:#121212") Serviço
  div.detalhes
    h1(style="color:#f1bc00") Olá.
    h4.text-black Somos uma agência de marketing digital.
    div(
      style="margin-left:40px"
    )
      p(
        style="margin:0"
      ) Lorem ipsum dolor sit amet consectetur eiusmod tempor incididunt labore magna ut enim ad minim veniam nostrud.
      p(
        style="margin:0;font-weight:bold;text-decoration:underline;cursor:pointer;color:#121212"
      ) BOTAO
</template>

<style scoped>
.container{
  display: flex;
  margin-top: 50px;
  margin-bottom: 50px;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
.icones {
  width: 60%;
  justify-content: space-between;
  flex-direction: row;
  display: flex;
}
.icones>div {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}
.detalhes {
  flex-direction: row;
  display: flex;
  width: 60%;
  justify-content: space-between;
  align-items: center;
  text-align: right;
}
.detalhes>div>p {
  text-align: left;
}
</style>
