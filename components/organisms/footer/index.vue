<script setup lang="ts">

const socials = [
    {
        id: 1,
        socialLink: 'https://www.facebook.com/heitor.schleder',
        icon: 'brand-facebook'
    },
    {
        id: 2,
        socialLink: 'https://www.instagram.com/heitor_schleder/?hl=pt-br',
        icon: 'brand-instagram'
    },
    {
        id: 3,
        socialLink: 'https://github.com/heitorschleder',
        icon: 'brand-github'
    },
    {
        id: 4,
        socialLink: 'https://www.linkedin.com/in/heitor-de-oliveira-schleder-10345a1ab/',
        icon: 'brand-linkedin'
    }]
</script>
<template>
    <footer class="flex items-center justify-center bg-yellow-500 font-black text-black h-32">
        <span class="mr-4 text-1xl sm:text-3xl">Follow Me:</span>
        <section id="socials" class="flex">
            <div v-for="social in socials" :key="social.id" class="mx-2 hover:scale-105 duration-200">
                <a :href="social.socialLink">
                    <i :class="`ti text-3xl sm:text-7xl ti-${social.icon}`"></i>
                </a>
            </div>
        </section>
    </footer>
</template>