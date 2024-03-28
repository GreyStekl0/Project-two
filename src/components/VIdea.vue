<script setup>
const idea = [
  {
    img: {
      src:"/Timetable.png",
      alt:"Timetable"
    },
  h3:"Составьте расписание",
  text:"Выберите время, предмет и класс. <br> Ученики получат уведомление о <br> предстоящем уроке."
  },
  {
    img: {
      src:"/Group.png",
      alt:"Group"
    },
    h3:"Подготовьте материал",
    text:"Загружайте необходимые материалы <br> к уроку"
  },
  {
    img: {
      src:"/Lesson.png",
      alt:"Lesson"
    },
    h3:"Начните урок с учениками",
    text:"Задавайте вопросы и вызывайте <br> «к доске» детей с поднятой рукой."
  },

]
</script>

<template>
  <section class="idea">
    <div class="container">
      <h2>
        Как это работает?
      </h2>
      <div class="row">
        <div class="col-sm-4"
             v-for="(item,index) in idea"
             :key="index">
          <div class="idea__Card">
            <div class="idea__Card-img-wrap">
              <img :src="item.img.src" :alt="item.img.alt">
            </div>
            <div class="idea__Card-h3">
              {{ item.h3 }}
            </div>
            <div class="idea__Card-text" v-html="item.text">
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>