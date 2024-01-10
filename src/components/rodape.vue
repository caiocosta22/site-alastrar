<script setup>
import { ref } from "vue";
const copyright = ref("Copyright © 2023 | ALASTRAR PROPAGANDA E MARKETING LTDA 32.756.301/0001-36");
const endereco = ref("Avenida Bezerra de Menezes, 1250 Sala 1902, São Gerardo, Fortaleza, CE CEP: 60325-001 | Fone: (85) 2139-1469");
</script>

<template lang="pug">
div.container
  div.interno
    div.logo.q-py-xl
      img(
        src="/icons/icon.png"
      )
    div.flex.column
      p(
        style="margin:0"
      ) {{ copyright }}
      p(
        style="margin:0"
      ) {{ endereco }}
    div
      q-icon(
          name="fa-brands fa-whatsapp"
          color="white"
          size="sm"
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
  margin: 0 auto;
  width: 60%;
  text-align: center;
  align-items: center;
}
p{
  font-size:12px;
  font-weight: 400;
  color:#fff;
}
</style>
