<script setup>
import { ref, onBeforeMount } from "vue";
import AOS from "aos";
import "aos/dist/aos.css";

const menus = ref(
  [
    {
      descricao: "trabalhos",
      banner: "/images/teste/1.png",
      id: 1
    },
    {
      descricao: "sobre nós",
      banner: "/images/teste/2.png",
      id: 2
    },
    {
      descricao: "fala com a gente",
      banner: "/images/teste/3.png",
      id: 3
    },
    {
      descricao: "nosso QG",
      banner: "/images/teste/4.png",
      id: 4
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
      div.foto
        img(
          v-if="menuselecionado.banner"
          :src="menuselecionado.banner"
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
  border: solid 1px blue;
  justify-content: center;
  display: flex;
  flex-direction: column;
}
.conteudo{
  width: 50%;
  height: 100%;
  border: solid 1px yellow;
  display: flex;
}
img {
  display: block;
  max-width: 100%;
  height: 100%;
}
</style>
