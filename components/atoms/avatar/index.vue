<script setup lang="ts">
import { defineProps } from 'vue'

const props = defineProps<{
    src: string
}>()
</script>

<template>
    <img class="w-60 h-60" :src="src" alt="avatar">
</template>