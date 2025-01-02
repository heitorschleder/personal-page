<script setup lang="ts">
import Avatar from '~/components/atoms/avatar/index.vue'
import Title from '~/components/atoms/title/index.vue'
import HeitorPic from '@/assets/images/heitordev.png'

const avatarSrc = HeitorPic

</script>
<template>
    <section class="text-center">
        <Avatar :src="avatarSrc"/>
        <Title :title="'Heitor Schleder'"/>
        <p>Dev Front-end</p>
    </section>
</template> 