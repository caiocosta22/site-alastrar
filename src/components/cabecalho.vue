<script setup>
import { ref, onMounted, onBeforeUnmount, onBeforeMount } from "vue";
import { useRouter, useRoute } from "vue-router";

const router = useRouter();

const drawer = ref(false);
const cor = ref();
const corbg = ref();
const logo = ref();

const menus = ref(
  [
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
  ]
);

const icons = ref([
  { name: "fa-brands fa-whatsapp" },
  { name: "fa-brands fa-instagram" },
  { name: "fa-brands fa-linkedin-in" }
]);

const handleScroll = () => {
  const scrollPosition = window.scrollY;
  if (scrollPosition === 0) {
    corbg.value = "rgba(0,0,0,0)";
    cor.value = "black";
    logo.value = "/images/logo.png";
  } else {
    corbg.value = "rgba(0,0,0,1)";
    cor.value = "white";
    logo.value = "/images/logo-branca.png";
  }
};

function redirectToHomePage () {
  router.push("/");
}

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onBeforeMount(() => {
  handleScroll();
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", handleScroll);
});

</script>

<template lang="pug">
div.container(
  :style="{backgroundColor:corbg}"
)
  q-toolbar.cabecalho
    div.logo
      q-img.imagem(
        :src="logo"
        @click="redirectToHomePage"
        style="cursor:pointer"
      )
    div.menus(
      :style="{color:cor}"
      :color="corcabecalho"
    )
      template(
        v-for="item in menus"
        :key="item"
      )
        p.texto.cursor-pointer(
        ) {{ item.menu }}
    div
      a(
        v-for="icone in icons"
        :key="icone"
      )
        q-icon.cursor-pointer.escala(
          :color="cor"
          size="xs"
          :name="icone.name"
        )
      a.botaomenu
        q-btn.botaomenu(
          flat
          @click="drawer = !drawer"
          round
          dense
          size="md"
          icon="menu"
          :color="cor"
        )
</template>

<style scoped>
.container{
  position: absolute;
  width: 100%;
  transition: background-color 0.6s ease-in;
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
  font-weight: 400;
  line-height: normal;
  padding-left: 30px;
  padding-top: 15px
}
.texto:hover{
  font-weight: bold;
}
.escala:hover{
  transform: scale(1.5);
  transition: 0.2s ease-in-out;
}
.botaomenu:hover {
  transform: rotate(180deg);
  transition: transform .5s ease-in-out;
}
@media screen and (min-width: 1024px) {
  .botaomenu{
    display:none
  }
}
@media screen and (max-width: 1024px) {
  .menus{
    display:none
  }
}
</style>
