<script setup>
import { ref, onBeforeMount } from "vue";
import AOS from "aos";
import "aos/dist/aos.css";

const menus = ref(
  [
    {
      descricao: "trabalhos",
      banner: [
        { foto: "/images/teste/1.png" },
        { foto: "/images/teste/1.png" },
        { foto: "/images/teste/1.png" },
        { foto: "/images/teste/1.png" }
      ],
      id: 1,
      subtitulo: "nossos trabalhos."
    },
    {
      descricao: "sobre nós",
      banner: [
        { foto: "/images/teste/2.png" },
        { foto: "/images/teste/2.png" },
        { foto: "/images/teste/2.png" },
        { foto: "/images/teste/2.png" }
      ],
      id: 2,
      subtitulo: "nossa história."
    },
    {
      descricao: "fala com a gente",
      banner: [
        { foto: "/images/teste/3.png" },
        { foto: "/images/teste/3.png" },
        { foto: "/images/teste/3.png" },
        { foto: "/images/teste/3.png" }
      ],
      id: 3,
      subtitulo: "formas de contatar."
    },
    {
      descricao: "nosso QG",
      banner: [
        { foto: "/images/teste/4.png" },
        { foto: "/images/teste/4.png" },
        { foto: "/images/teste/4.png" },
        { foto: "/images/teste/4.png" }
      ],
      id: 4,
      subtitulo: "onde estamos."
    }
  ]
);

const menuselecionado = ref();

function selectMenu (id) {
  menuselecionado.value = menus.value.find(menu => menu.id === id);
}

onBeforeMount(() => {
  selectMenu(1);
  AOS.init({
    duration: 700,
    once: true,
    delay: 200,
    easing: "ease-in-out"
  });
});

</script>

<template lang="pug">
div.container
  div.interno(
    data-aos="fade-down"
  )
    div.menus
      div(
        v-for="menu in menus"
        :key="menu"
      )
        span(
          @click="selectMenu(menu.id)"
          :class="{ 'sobrelinha': menuselecionado.id === menu.id }"
        ) {{ menu.descricao }}
    div.conteudo
      div.foto(
        v-for="fotos in menuselecionado.banner"
        :key="fotos"
      )
        img(
          v-if="fotos.foto"
          :src="fotos.foto"
        )
        div.overlay
          div.overlay2
            div.textos
              div.text2 clique para explorar
            q-icon(
              name="fa-solid fa-arrow-right"
              size="sm"
              color="white"
            )
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: linear-gradient(0deg, #cacaca, #a9a9a9);
}
.interno {
  display: flex;
  width: 90%;
  margin: 0 auto;
  flex-direction: column;
  flex-wrap: nowrap;
  height: 100%;
}
span {
  color:#121212;
  font-weight: 400;
  text-align: left;
  margin: auto;
  font-size: 45px;
  cursor: pointer;
  transition: 0.5s ease-in-out;
}
span:hover{
  text-decoration: underline;
}
.sobrelinha{
  text-decoration: underline;
}
.menus{
  justify-content:space-evenly;
  display: flex;
  flex-direction: row;
}
.conteudo{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
}
.foto{
  position: relative;
  cursor: pointer;
  max-width: 100%;
  display: block;
}
img {
  display: block;
  max-width: 100%;
  height: 100%;
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
  transition: 0.5s ease;
  background-color: #4b2059;
  opacity: 0;
  z-index: 1;
}
.foto:hover .overlay {
  opacity: 0.9;
}
.textos{
  position: absolute;
  top: 85%;
  left: 5%;
  z-index: 4;
  opacity: 1;
  flex-direction: column;
  display: flex;
  align-items: flex-start;
}
.text {
  color: #fff;
  font-weight: 500;
  font-size: 20px
}
.text2 {
  color: #fff;
  font-weight: bold;
  font-size: 30px
}
.q-icon{
  top: 5%;
  left: 90%;
  z-index: 4;
  position: absolute;
}

</style>
