<template>
  <div class="wrapper">
    <TheSidebar />
    <TheHeader />
    <MainPage />
    <TheFooter />
  </div>
</template>

<script>
import TheSidebar from './components/TheSidebar.vue'
import TheHeader from './components/TheHeader.vue'
import MainPage from './components/MainPage.vue'
import TheFooter from './components/TheFooter.vue'

export default {
  name: 'App',
  components: {
    TheSidebar,
    TheHeader,
    MainPage,
    TheFooter,
  },
}
</script>
