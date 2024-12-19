<script setup>
import { ref } from 'vue';

const items = ref([
    {
        thumb: 'https://kronus.kebook.com.br/assets/f6185048-b91c-438e-810f-6ad0ac94e06c.png&quot;',
        projectTitle: 'Teste1',
        projectDesc: 'desced as das dasd adas dadasda asdasd adasdadads',
        skills: ''
    },
    {
        thumb: 'https://kronus.kebook.com.br/assets/f6185048-b91c-438e-810f-6ad0ac94e06c.png&quot;',
        projectTitle: 'Teste2',
        projectDesc: 'desced as das dasd adas dadasda asdasd adasdadads',
        skills: ''
    },
    {
        thumb: 'https://kronus.kebook.com.br/assets/f6185048-b91c-438e-810f-6ad0ac94e06c.png&quot;',
        projectTitle: 'Teste3',
        projectDesc: 'desced as das dasd adas dadasda asdasd adasdadads',
        skills: ''
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
</script>

<template>
    <div class="slider mt-8 z-10">
        <div v-for="(item, index) in items" :key="index" class="item" :style="getItemStyle(index)">
            <img :src="item.thumb" alt="thumb" class='thumb rounded-t-lg h-32'>
            <div class="text-white text-center mt-3">
                <h1 class="font-black">{{ item.projectTitle }}</h1>
                <p class="font-black">{{ item.projectDesc }}</p>
            </div>
        </div>
        <button id="next" @click="nextSlide">> </button>
        <button id="prev" @click="prevSlide">< </button>
    </div>
</template>

<style scoped>
.thumb {
    border-radius: ;
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
    height: 280px;
    text-align: justify;
    background-color: #1a1919ce;
    border-radius: 10px;
    padding: 20px;
    transition: 0.5s;
    left: calc(50% - 150px);
    top: 0;
}

#next {
    position: absolute;
    right: 10rem;
    top: 40%;
}

#prev {
    position: absolute;
    left: 10rem;
    top: 40%;
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
</style>