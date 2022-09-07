<template>
  <div class="slider">
    <span class="slider__nums">{{ currentSlide + 1 }}/{{ slides.length }}</span>
    <div class="slider__inner">
      <SliderItem v-for="(slide, idx) in slides" :key="`slide-${idx}`" :slide="slide" :currentSlide="currentSlide" :idx="idx" />
    </div>

    <button type="button" class="slider__btn" @click="toNext"></button>
  </div>
</template>

<script>
import SliderItem from './SliderItem.vue'
export default {
  components: { SliderItem },
  data() {
    return {
      slides: [
        {
          img: 'slide-image-1',
          text: 'Подсказка № 1: Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите на паузу — ему не терпится отдать вам промокод.',
        },
        {
          img: 'slide-image-2',
          text: 'Подсказка № 2: Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите на паузу — ему не терпится отдать вам промокод',
        },
        {
          img: 'slide-image-3',
          text: 'Подсказка № 3: Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите на паузу — ему не терпится отдать вам промокод',
        },
        {
          img: 'slide-image-1',
          text: 'Подсказка № 4:Для примера мы показали вам его лицо. В первой серии он прячется в подвале за мониторами, и пусть борода не собьёт вас с толку. Найдите героя и нажмите на паузу — ему не терпится отдать вам промокод',
        },
      ],
      currentSlide: 0,
      slideInterval: null,
    }
  },
  methods: {
    toNext() {
      const idx = this.currentSlide < this.slides.length - 1 ? this.currentSlide + 1 : 0
      this.setCurrentSlide(idx)
    },
    setCurrentSlide(idx) {
      this.currentSlide = idx
    },
  },
  mounted() {
    this.slideInterval = setInterval(() => {
      this.toNext() 
    }, 5000)
  },
  beforeUnmount() {
    clearImmediate(this.slideInterval)
  },
}
</script>
