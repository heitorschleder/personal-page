<script setup lang="ts">
import Header from '../components/organisms/header/index.vue'
import Slider from '../components/organisms/slider/index.vue'
import Title from '../components/atoms/title/index.vue'
</script>
<template>
  <div class="content-manager -z-10">
    <Header />
    <Title class="mt-20" :title="'Projects'" />
    <Slider />
    <Title class="mt-20" :title="'Skills'" />
    <Title class="mt-20" :title="'Certified'" />
    <Title class="mt-20" :title="'Hobbies'" />
  </div>
</template>
<style scoped>
.content-manager {
  background-image: url(../assets/images/background.jpeg);
}
</style>