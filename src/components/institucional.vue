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
        name="fa-solid fa-spinner"
        color="info"
        size="xl"
      )
      p(style="font-size:18px;color:#121212") Serviço
  div.detalhes
    div(
      style="width:15%; text-align:left"
    )
      h2(
        style="color:#f1bc00;"
      ) Olá.
    div.text-black(
      style="width:35%;text-align:left"
    )
      h4 Somos uma agência de marketing digital.
    div(
      style="width:50%; text-align:right"
    )
      p(
      ) Lorem ipsum dolor sit amet consectetur eiusmod tempor incididunt labore magna ut enim ad minim veniam nostrud.
</template>

<style scoped>
.container{
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  margin-top: 30px;
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
  align-items: center;
  text-align: center;
  justify-content: space-between;
}
.detalhes>div {
  text-align: center;
  display: inline-block;
}
</style>
