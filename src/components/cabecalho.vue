<script setup>
import { ref, onMounted } from "vue";
import { useRouter, useRoute } from "vue-router";

const router = useRouter();
const route = useRoute();

const corcabecalho = ref("black");
const corhexa = ref("rgba(0,0,0,1)");
const corbg = ref("rgba(0,0,0,0)");

const menus = ref([
  {
    menu: "Home",
    submenu: [
      "1",
      "2"
    ]
  },
  {
    menu: "Portfolio",
    submenu: [
      "1",
      "2"
    ]
  },
  {
    menu: "Clientes",
    submenu: [
      "1",
      "2"
    ]
  },
  {
    menu: "Páginas",
    submenu: [
      "1",
      "2"
    ]
  },
  {
    menu: "Contato",
    submenu: [
      "1",
      "2"
    ]
  }
]);

const handleScroll = () => {
  const scrollPosition = window.scrollY;
  const opacityThreshold = 0;
  if (scrollPosition > opacityThreshold) {
    corcabecalho.value = "white";
    corhexa.value = "rgba(255,255,255,1)";
    corbg.value = "rgba(0,0,0,1)";
  } else {
    corcabecalho.value = "black";
    corhexa.value = "rgba(0,0,0,1)";
    corbg.value = "rgba(0,0,0,0)";
  }
};

function redirectToHomePage () {
  router.push("/");
}

onMounted(() => {
  if (route.path === "/") {
    window.addEventListener("scroll", handleScroll);
  }
});
</script>

<template lang="pug">
div.container(
  :style="{backgroundColor:corbg}"
)
  q-toolbar.cabecalho
    div.logo
      q-img.imagem(
        src="/images/logo.png"
        spinner-colow="white"
        @click="redirectToHomePage"
        style="cursor:pointer"
      )
    div.menus(
      :style="{color:corhexa}"
      :color="corcabecalho"
    )
      template(
        v-for="item in menus"
        :key="item"
      )
        p.texto.cursor-pointer(
        ) {{ item.menu }}
    div
      a
        q-icon.cursor-pointer(
          :color="corcabecalho"
          size="xs"
          name="fa-brands fa-whatsapp"
        )
      a
        q-icon.cursor-pointer(
          :color="corcabecalho"
          size="xs"
          name="fa-brands fa-instagram"
        )
      a
        q-icon.cursor-pointer(
          :color="corcabecalho"
          size="xs"
          name="fa-brands fa-linkedin-in"
        )
</template>

<style scoped>
.container{
  position: absolute;
  width: 100%;
  transition: background-color 0.5s;
}
.cabecalho {
  display: flex;
  flex-direction: row;
  flex-shrink: 1;
  flex-grow: 1;
  max-width: 90%;
  margin: 0 auto;
  justify-content:space-between;
  align-items: center;
  text-align: center;
}
.logo {
  width: 144px;
}
.imagem {
  display: flex;
  height:80px
}
.menus{
  display: flex;
  flex-direction: row;
  text-align: center;
}
div>a {
  padding-left: 30px;
}
.texto {
  font-family: Montserrat;
  font-size: 16px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  padding-left: 30px;
  padding-top: 15px
}
.texto:hover{
  font-weight: bold;
}
</style>
