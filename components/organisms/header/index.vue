<script setup lang="ts">
import Avatar from '~/components/atoms/avatar/index.vue'

const avatarSrc = 'https://kronus.kebook.com.br/assets/8898e345-c657-4704-be94-a853cca535b5/expert-mid.png.webp?format=webp&quality=80'

</script>

<template>
    <header class="flex m-9 justify-center">
        <Avatar :src="avatarSrc"/>
    </header>
</template>