<template>
  <transition name="slide-in">
    <div v-show="currentSlide===idx" class="slider__item">
      <div class="slider__img">
    <img :src="require(`../assets/images/${slide.img}.png`)" alt="" />
  </div>
  <div class="slider__text">{{ slide.text }}</div>
  </div>
  </transition>
  

</template>

<script>
export default {
  props: {
    slide: {
      type: Object,
      default: () => {},
    },
    currentSlide: {
      type: Number,
      default: 0
    },
    idx:{
      type: Number,
      default: 0
    }
  },
}
</script>

<style>
  .slide-in-enter-active,
  .slide-in-leave-active{
    transition: all 1s ease-in-out;
  }
  .slide-in-enter-from{
    transform: translateX(100%);
  }
  .slide-in-leave-to{
    transform: translateX(-100%);
  }
</style>
