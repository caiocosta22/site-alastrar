<script setup>
import { ref, onBeforeMount } from "vue";
import AOS from "aos";
import "aos/dist/aos.css";

const chamada = ref("Promova,<br>Propague<br>Espalhe");

onBeforeMount(() => {
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
  q-parallax(
    src="/images/banner.jpg"
    height="1080"
    data-aos="fade-left"
  )
    div.column(
      style="width:90%; align-items:start; justify-content: center"
      data-aos="fade-left"
    )
      h1(
        v-html="chamada"
      )
      q-btn.escala(
        style="width:300px; border-radius: 20px; margin-top:20px"
        color="secondary"
        push
      )
        p(
          style="margin:0"
          color="white"
        ) CLIQUE PARA ALASTRAR
</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #edae01;
}
h1 {
  color:#121212;
  font-weight: 600;
  text-align: left;
  margin: 0;
  font-size: 85px
}
.escala:hover{
  transform: scale(1.2);
  transition: 0.5s ease-in-out;
}
</style>
