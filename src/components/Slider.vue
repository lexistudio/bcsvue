<template>
  <div class="card">
    <swiper
      :spaceBetween="32"
      slidesPerView="3"
      :autoplay="false"
      :centeredSlides="false"
      :breakpoints="{
        1400: {
          slidesPerView: 3,
          spaceBetween: 16,
        },
        768: {
          slidesPerView: 2,
          spaceBetween: 16,
        },
        320: {
          slidesPerView: 1,
          spaceBetween: 6,
        },
      }"
    >
      <swiper-slide v-for="item in sl" :key="item.id" :class="[item.color, item.filter === filters ? 'active' : '']">
        <div class="card__body">
          <div class="card__title" v-html="item.name"></div>
          <div class="card__icon">
            <img :src="`/assets/img/${item.icon}.svg`" :alt="item.name" />
          </div>
          <div class="card__group">
            <div
              class="card__group_item"
              v-for="itm in item.price"
              :key="itm.id"
            >
              <div class="card__group_title">{{ itm.name }}</div>
              <div class="card__group_subTitle">{{ itm.subName }}</div>
            </div>
          </div>
        </div>
        <div class="card__result">
          <div class="card__result_title">{{ item.result }}%</div>
          <div class="card__result_subtitle">максимальная доходность</div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "@popsicle/vue-swiper";

export default {
  component: {
    swiper: "Swiper",
    "swiper-slide": "SwiperSlide",
  },
  props: {
    filters: {
      type: String,
    },
  },
  data() {
    return {
      sl: [
        {
          id: 1,
          name: "защищённые<br>инвестиции в Alibaba",
          filter: "one",
          icon: "alibaba",
          color: "swiper-slide-orange",
          price: [
            { id: 1, name: "3 мес.", subName: "срок размещения" },
            { id: 2, name: "от 300 000 ₽", subName: "минимальная сумма" },
          ],
          result: 10,
        },
        {
          id: 2,
          name: "Нота №81<br>«Мультибарьер»",
          filter: "two",
          icon: "multi",
          color: "swiper-slide-black",
          price: [
            { id: 1, name: "от 1 250 $", subName: "минимальная сумма" },
            { id: 2, name: "5 лет", subName: "срок размещения" },
          ],
          result: 15,
        },
        {
          id: 3,
          name: "защищённые<br>инвестиции в сбербанк",
          filter: "three",
          icon: "sber",
          color: "swiper-slide-green",
          price: [
            { id: 1, name: "3 мес.", subName: "срок размещения" },
            { id: 2, name: "от 300 000 ₽", subName: "минимальная сумма" },
          ],
          result: 10,
        },
      ],
    };
  },
};
</script>
