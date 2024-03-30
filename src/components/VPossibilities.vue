<script setup>
import {Swiper} from "swiper";
import { onMounted } from 'vue'
import {Navigation, Pagination} from "swiper/modules";

const possibilities = [
  {
    img: {
      src:"/possibilities_1.svg",
      alt:"possibilities1"
    },
    h2: "Общение с классом",
    text: "Видеосвязь<br>Чат с классом"
  },
  {
    img: {
      src:"/possibilities_2.svg",
      alt:"possibilities2"
    },
    h2: "Проведение занятий",
    text: "Презентация файлов\n" +
        "Демонстрация экрана"
  },
  {
    img: {
      src:"/possibilities_3.svg",
      alt:"possibilities3"
    },
    h2: "Посещаемость",
    text: "Автоматическое<br>отслеживание<br>присутствующих"
  },
  {
    img: {
      src:"/possibilities_4.svg",
      alt:"possibilities4"
    },
    h2: "История занятий",
    text: "Материалы урока"
  }
]

let swiper;

onMounted(() => {
  swiper = new Swiper(".mySwiper", {
    modules: [Navigation, Pagination],
    spaceBetween: 10,
    pagination: {
      el: ".swiper-pagination",
    },
  });
});

</script>

<template>
  <section class="possibilities">
    <div class="container">
      <h2>
        Возможности
      </h2>
      <div class="row">
        <div class="col-6 col-lg-3 d-none d-sm-block"
             v-for="(item,index) in possibilities"
             :key="index">
          <div :class="`possibilities__Card possibilities__Card-${index}`">
            <div class="possibilities__Card-img-wrap">
              <img :src="item.img.src" :alt="item.img.alt">
            </div>
            <div class="possibilities__Card-h2">
              {{ item.h2 }}
            </div>
            <div class="possibilities__Card-text" v-html="item.text">
            </div>
          </div>
        </div>
        <div class="swiper mySwiper">
          <div class="swiper-wrapper">
            <div class="swiper-slide"
                 v-for="(item, index) in possibilities"
                 :key="index">
              <div :class="`possibilities__Card possibilities__Card-${index}`" :id="`possibilities-card-${index}`">
                <div class="possibilities__Card-img-wrap">
                  <img :src="item.img.src" :alt="item.img.alt">
                </div>
                <div class="possibilities__Card-h2">
                  {{ item.h2 }}
                </div>
                <div class="possibilities__Card-text" v-html="item.text">
                </div>
              </div>
            </div>
          </div>
          <div class="swiper-pagination"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.swiper{
  width: 296px;
  height: 100%;
}
.swiper-pagination {
  position: relative;
  padding-top: 16px;
}
</style>