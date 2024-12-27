<script setup lang="ts">
import Header from '../components/organisms/header/index.vue'
import Slider from '../components/organisms/slider/index.vue'
import Title from '../components/atoms/title/index.vue'
import Skills from '../components/organisms/skills/index.vue'
import Carousel from '../components/organisms/carousel/index.vue'
import Footer from '../components/organisms/footer/index.vue'
</script>
<template>
  <div class="content-manager -z-10">
    <Header />
    <Title class="mt-20" :title="'Projects'" />
    <Slider />
    <Title class="mt-20" :title="'Skills'" />
    <Skills />
    <Title class="mt-40" :title="'Certified'" />
    <Carousel />
    <Footer class="mt-20" />
  </div>
</template>
<style scoped>
.content-manager {
  background-image: url(../assets/images/background.jpeg);
}
</style>