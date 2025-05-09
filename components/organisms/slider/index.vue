<script setup>
import { ref } from 'vue';
import todoImage from '@/assets/images/project-todo.png'
import pokeImage from '@/assets/images/project-pokedex.png'
import converterImage from '@/assets/images/project-converter.png'
import webImage from '@/assets/images/project-first.png'
import emailImage from '@/assets/images/project-email.png'
import shippingImage from '@/assets/images/project-shipping.png'
import carsImage from '@/assets/images/project-cars.png'

const items = ref([
    {
        repository: 'https://github.com/heitorschleder/to-do-list',
        thumb: todoImage,
        projectTitle: 'To-Do List',
        projectDesc: 'A to-do list made with Vue2 and Vuex, the name already says what this project does',
        additionalInfo: [{
            skill: "vue",
            percentage: "88.6%"
        },
        {
            skill: "html",
            percentage: "2.6%"
        },
        {
            skill: "javascript",
            percentage: "8.8%"
        },
        ],
        showMore: false
    },
    {
        repository: 'https://github.com/heitorschleder/shipping-quote-app',
        thumb: shippingImage,
        projectTitle: 'Shipping Quote Calculator',
        projectDesc: 'Here you can get a quote from one CEP code to another',
        additionalInfo: [{
            skill: "vue",
            percentage: "71%"
        },
        {
            skill: "typescript",
            percentage: "25.3%"
        },
        {
            skill: "javascript",
            percentage: "1.6%"
        }
        ],
        showMore: false
    },
{
        repository: 'https://github.com/heitorschleder/ecommerce-cars-test',
        thumb: carsImage,
        projectTitle: 'Landing Page',
        projectDesc: 'This is a test for a bigger project',
        additionalInfo: [{
            skill: "typescript",
            percentage: "98.4%"
        },
        {
            skill: "CSS",
            percentage: "1.4%"
        },
        {
            skill: "javascript",
            percentage: "0.2%"
        }
        ],
        showMore: false
    },
    {
        repository: 'https://github.com/heitorschleder/Pokedex',
        thumb: pokeImage,
        projectTitle: 'Pokedex',
        projectDesc: 'A simple Pokedex application to view Pokemon details.',
        additionalInfo: [{
            skill: "javascript",
            percentage: "38.1%"
        },
        {
            skill: "css",
            percentage: "37%.1"
        },
        {
            skill: "html",
            percentage: "24%.8"
        },
        ], showMore: false
    },
    {
        repository: 'https://github.com/heitorschleder/Conversor',
        thumb: converterImage,
        projectTitle: 'Conversor',
        projectDesc: 'project with API consumption for training',
        additionalInfo: [{
            skill: "vue",
            percentage: "74.6%"
        },
        {
            skill: "html",
            percentage: "15.6%"
        },
        {
            skill: "javascript",
            percentage: "9.8%"
        },
        ], showMore: false
    },
    {
        repository: 'https://github.com/heitorschleder/portfolio',
        thumb: webImage,
        projectTitle: 'First Web Page',
        projectDesc: 'One of my first studies results with html (nostalgic)',
        additionalInfo: [{
            skill: "html",
            percentage: "100%"
        }
        ], showMore: false
    },
    {
        repository: 'https://github.com/heitorschleder/email-marketing',
        thumb: emailImage,
        projectTitle: 'Email Marketing Template',
        projectDesc: 'Simple email marketing template, focuses on alignment and good practices in HTML.',
        additionalInfo: [{
            skill: "html",
            percentage: "100%"
        }
        ], showMore: false
    },
]);

const active = ref(0);

const getItemStyle = (index) => {
    const stt = Math.abs(active.value - index);
    const translateX = active.value < index ? 120 * stt : -120 * stt;
    const scale = 1 - 0.2 * stt;
    const opacity = stt > 2 ? 0 : 0.6;

    return {
        transform: `translateX(${translateX}px) scale(${scale}) perspective(16px)`,
        zIndex: stt === 0 ? 1 : -stt,
        filter: stt > 0 ? 'blur(5px)' : 'none',
        opacity: stt === 0 ? 1 : opacity,
    };
};

const nextSlide = () => {
    active.value = (active.value + 1) % items.value.length;
};

const prevSlide = () => {
    active.value = (active.value - 1 + items.value.length) % items.value.length;
};

const toggleMoreInfo = (index) => {
    items.value[index].showMore = !items.value[index].showMore;
};

</script>

<template>
    <div class="slider mt-8 z-10">
        <div v-for="(item, index) in items" :key="index" class="item h-auto" :style="getItemStyle(index)">
            <a :href="item.repository" class="relative group">
                <nuxt-img :src="item.thumb" :alt="item.projectTitle" class='thumb rounded-t-lg h-32 transition-opacity duration-300 group-hover:opacity-0' />
                <img src="~/assets/images/wanna-check.png" alt="wannacheck"
                    class="img-github rounded-t-lg absolute inset-0 opacity-0 transition-opacity duration-300 group-hover:opacity-100">
            </a>
            <div class="flex flex-col items-center text-white mt-3">
                <div class="mb-2">
                    <h1 class="font-black text-center">{{ item.projectTitle }}</h1>
                    <p class="font-thin text-start">{{ item.projectDesc }}</p>
                </div>
                <div :class="['additional-info transition-all', { 'show': item.showMore }]">
                    <div v-for="(add, index) in item.additionalInfo" :key="index">
                        <div class="flex justify-between border border-[#FFCD29] w-[300px] m-1">
                            <p class="ml-10">{{ add.skill }}</p>
                            <p class="mr-10">{{ add.percentage }}</p>
                        </div>
                    </div>
                </div>
                <button id="buttonMoreInfo"
                    class="mt-2 rounded-b-lg bg-[#FFCD29] w-full h-6 inset-x-0 bottom-0 hover:bg-[#CEAF30] hover:delay-75"
                    @click="toggleMoreInfo(index)">
                    <i :class="['text-black text-xl ti', item.showMore ? 'ti-chevron-compact-up' : 'ti-chevron-compact-down']"></i>
                </button>
            </div>
        </div>
        <button id="next" @click="nextSlide">> </button>
        <button id="prev" @click="prevSlide">
            < </button>
    </div>
</template>

<style scoped>
.thumb {
    object-fit: cover;
}

.img-github{
    object-fit: cover;
    width: 48rem;
    height: 8rem;
}

.additional-info {
    overflow: hidden;
    max-height: 0;
    transition: max-height 0.5s ease;
}

.additional-info.show {
    max-height: 500px;
}

.slider {
    position: relative;
    width: 100%;
    height: 370px;
    overflow: hidden;
}

.item {
    position: absolute;
    width: 350px;
    text-align: justify;
    background-color: #1a1919ce;
    border-radius: 10px;
    padding: 20px;
    transition: 0.5s;
    left: calc(50% - 175px);
    top: 0;
}


#next {
    position: absolute;
    right: 10rem;
    top: 80%;
}

#prev {
    position: absolute;
    left: 10rem;
    top: 80%;
}

#prev,
#next {
    color: #fff;
    background: none;
    border: none;
    font-size: xxx-large;
    font-family: monospace;
    font-weight: bold;
    opacity: 0.5;
    transition: opacity 0.5s;
}

#prev:hover,
#next:hover {
    opacity: 1;
}

@media (max-width: 440px) {
    #next {
        right: 5rem;
    }
    #prev {
        left: 5rem;
    }
}

</style>