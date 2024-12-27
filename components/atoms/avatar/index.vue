<script setup lang="ts">
import { defineProps } from 'vue'

const props = defineProps<{
    src: string
}>()
</script>

<template>
    <nuxt-img class="w-60 h-60 mt-9" :src="src" alt="avatar"/>
</template>