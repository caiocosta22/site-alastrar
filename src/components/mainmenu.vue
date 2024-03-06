<script setup>
import { ref, onBeforeMount } from "vue";
import AOS from "aos";
import "aos/dist/aos.css";

const menus = ref(
  [
    {
      descricao: "trabalhos",
      banner: "/images/teste/1.png",
      id: 1,
      subtitulo: "nossos trabalhos."
    },
    {
      descricao: "sobre nós",
      banner: "/images/teste/2.png",
      id: 2,
      subtitulo: "nossa história."
    },
    {
      descricao: "fala com a gente",
      banner: "/images/teste/3.png",
      id: 3,
      subtitulo: "formas de contatar."
    },
    {
      descricao: "nosso QG",
      banner: "/images/teste/4.png",
      id: 4,
      subtitulo: "onde estamos."
    }
  ]
);

const fotos = ref([
  { banner: "/images/teste/4.png" },
  { banner: "/images/teste/4.png" },
  { banner: "/images/teste/4.png" },
  { banner: "/images/teste/4.png" },
  { banner: "/images/teste/4.png" },
  { banner: "/images/teste/4.png" },
  { banner: "/images/teste/4.png" },
  { banner: "/images/teste/4.png" }
]);

const menuselecionado = ref();
const ativo = ref(0);

function ativaSlide (id) {
  ativo.value = id;
}

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
    template(
      v-if="ativo===0"
    )
      div.menus(
        data-aos="fade-down"
      )
        div(
          v-for="menu in menus"
          :key="menu"
        )
          span(
            @click="selectMenu(menu.id)"
            :class="{ 'sobrelinha': menuselecionado.id === menu.id }"
          ) {{ menu.descricao }}
      div.conteudo(
        data-aos="fade-down"
      )
        div.foto
          img(
            v-if="menuselecionado.banner"
            :src="menuselecionado.banner"
          )
          div.overlay(
            @click="ativaSlide(1)"
          )
            div.overlay2
              div.textos
                div.text2clique para explorar
              q-icon.icone(
                name="fa-solid fa-arrow-right"
                size="sm"
                color="white"
              )
    template(
      v-if="ativo===1"
    )
      div.apresentacao(
        data-aos="fade-left"
      )
        div(
          @click="ativaSlide(0)"
          style="display:flex; align-items:center; flex-direction:row; justify-content:start; width:5%; margin-top:20px; gap:5px"
        )
          span voltar
        div.grid(
          style="display:grid;grid-template-columns:repeat(4,1fr)"
        )
          div.foto(
            v-for="item in fotos"
            :key="item"
          )
            img(
              :src="item.banner"
            )
            div.overlay
            div.overlay2
              div.textos
                div.text
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
  flex-direction: row;
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
  width: 50%;
  justify-content: center;
  display: flex;
  flex-direction: column;
}
.conteudo{
  width: 50%;
  height: 100%;
  display: flex;
}
.apresentacao{
  width: 100%;
  display: flex;
  height: 100%;
  flex-direction: column;
  gap: 20px;
}
.foto{
  position: relative;
  cursor: pointer;
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
  top: 90%;
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
.icone{
  top: 5%;
  left: 95%;
  z-index: 4;
  position: absolute;
}

</style>
