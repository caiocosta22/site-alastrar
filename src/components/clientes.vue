<script setup>
import { ref } from "vue";

const fotos = ref([
  {
    colorida: "/images/clientes/1.png",
    cinza: "images/clientescinza/1.png",
    exibircor: false
  },
  {
    colorida: "/images/clientes/2.png",
    cinza: "images/clientescinza/2.png",
    exibircor: false
  },
  {
    colorida: "/images/clientes/3.png",
    cinza: "images/clientescinza/3.png",
    exibircor: false
  },
  {
    colorida: "/images/clientes/4.png",
    cinza: "images/clientescinza/4.png",
    exibircor: false
  }
]);

const alterarImagem = (foto) => {
  foto.exibircor = !foto.exibircor;
};
</script>

<template lang="pug">
div.titulo.text-center
  h2(
    style="font-weight:500;font-size:35px"
  ) Nossos clientes de sucesso
div.container
  div.interno
    template(
        v-for="foto in fotos"
        :key="foto"
      )
        div.clientes
          img(
            :src="foto.exibircor ? foto.colorida : foto.cinza"
            @mouseover="() => alterarImagem(foto)"
            @mouseout="() => alterarImagem(foto)"
          )
</template>

<style scoped>
.container {
  display: flex;
  margin: 0 auto;
  justify-content: center;
  align-items: center;
}
.interno {
  margin: 0 auto;
  width: 60%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.clientes {
  display: flex;
}
img {
  max-width: 100%;
  display: block;
  cursor: pointer;
  height: 100px;
  width: 100px;
  transition: filter 1s ease-in-out;
}

</style>
