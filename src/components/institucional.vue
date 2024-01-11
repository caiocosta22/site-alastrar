<script setup>
import { ref } from "vue";
import { Carousel, Slide } from "vue3-carousel";
import "vue3-carousel/dist/carousel.css";

const icons = ref([
  { icone: "/icons/alastrarcores/ICON-1.png", tag: "Serviço" },
  { icone: "/icons/alastrarcores/ICON-2.png", tag: "Serviço" },
  { icone: "/icons/alastrarcores/ICON-3.png", tag: "Serviço" },
  { icone: "/icons/alastrarcores/ICON-4.png", tag: "Serviço" },
  { icone: "/icons/alastrarcores/ICON-5.png", tag: "Serviço" },
  { icone: "/icons/alastrarcores/ICON-2.png", tag: "Serviço" },
  { icone: "/icons/alastrarcores/ICON-3.png", tag: "Serviço" },
  { icone: "/icons/alastrarcores/ICON-4.png", tag: "Serviço" },
  { icone: "/icons/alastrarcores/ICON-5.png", tag: "Serviço" }
]);

const settings = ref({
  snapAlign: "start",
  wrapAround: true,
  autoplay: 2500
});

const breakpoints = ref({
  368: {
    itemsToShow: 2.0
  },
  558: {
    itemsToShow: 2.0
  },
  768: {
    itemsToShow: 3.0
  },
  1024: {
    itemsToShow: 4.0
  },
  1280: {
    itemsToShow: 6.0
  }
});
</script>

<template lang="pug">
div.container
  Carousel(
    v-bind="settings"
    :breakpoints="breakpoints"
    style="width: 60%; margin: 0 auto;"
  )
    Slide(
      v-for="(icon,index) in icons"
      :key="index"
    )
      div.column(
        style="height: 100%;cursor:pointer"
      )
        div(
          style="height: 80%;"
        )
          img.carrossel(
            :src="icon.icone"
            spinner="white"
            style="width: 160px; margin:0 auto;"
          )
        div.q-pb-lg(
          style="height: 20%;"
        )
          p(
            style="margin: 0 auto; font-size:14px;font-weight:400"
          ) {{ icon.tag }}
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
.carousel__prev,
.carousel__next {
  box-sizing: content-box;
}
.carousel__slide p {
  height: 10%
}
</style>
