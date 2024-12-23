<script setup lang="ts">

const skills = [{
    id: 1,
    skillImg: 'brand-javascript',
    skillName: 'Javascript',
    skillWidth: 89
},
{
    id: 2,
    skillImg: 'brand-nuxt',
    skillName: 'Nuxt3',
    skillWidth: 74
},
{
    id: 3,
    skillImg: 'brand-vue',
    skillName: 'Vuex',
    skillWidth: 64
},
{
    id: 4,
    skillImg: 'brand-tailwind',
    skillName: 'TailwindCss',
    skillWidth: 89
},
{
    id: 5,
    skillImg: 'brand-html5',
    skillName: 'Html',
    skillWidth: 95
},
{
    id: 6,
    skillImg: 'brand-css3',
    skillName: 'Css3',
    skillWidth: 95
},
{
    id: 7,
    skillImg: 'brand-typescript',
    skillName: 'Typescript',
    skillWidth: 64
},
{
    id: 8,
    skillImg: 'sql',
    skillName: 'mySQL',
    skillWidth: 60
},
{
    id: 9,
    skillImg: 'brand-nodejs',
    skillName: 'NodeJs',
    skillWidth: 71
},
{
    id: 10,
    skillImg: 'brand-php',
    skillName: 'php',
    skillWidth: 30
},
{
    id: 11,
    skillImg: 'brand-docker',
    skillName: 'Docker',
    skillWidth: 70
},
{
    id: 12,
    skillImg: 'brand-aws',
    skillName: 'Aws',
    skillWidth: 65
},
{
    id: 13,
    skillImg: 'cloud',
    skillName: 'Google Cloud',
    skillWidth: 74
},
{
    id: 14,
    skillImg: 'brand-github',
    skillName: 'GitHub',
    skillWidth: 80
},
{
    id: 15,
    skillImg: 'brand-react',
    skillName: 'React',
    skillWidth: 18
},
{
    id: 16,
    skillImg: 'brand-graphql',
    skillName: 'GraphQL',
    skillWidth: 20
},
{
    id: 17,
    skillImg: 'ux-circle',
    skillName: 'UI/UX',
    skillWidth: 20
}]
</script>
<template>
    <section class="overflow-hidden h-60 w-80 flex flex-col justify-self-center text-center">
        
        <div class="overflow-y-auto h-full no-scrollbar">
            <div v-for="skill in skills" :key="skill.id">
                <div class="flex justify-around items-center mb-5 m-3">
                    <i :class="`ti text-7xl ti-${skill.skillImg}`"></i>
                    <h2 class="w-44">{{ skill.skillName }}</h2>
                    <div class="border border-yellow-600 h-6 w-20 p-[1px]">
                        <div class="bg-yellow-300 h-full" :style="`width: ${skill.skillWidth}%`"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>