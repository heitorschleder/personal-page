<script setup lang="ts">
import { defineProps } from 'vue'

const props = defineProps<{
    title: string
}>()
</script>
<template>
    <section class="text-center m-3 text-3xl">
        <h1>{{ title }}</h1>
    </section>
</template>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Rubik:ital,wght@0,300..900;1,300..900&display=swap');

h1 {
    font-family: "Rubik", serif;
    font-optical-sizing: auto;
    font-weight: 400;
    font-style: normal;
}
</style>
