<script setup>
import { ref } from 'vue';

const items = ref([
    {
        title: 'To-Do List',
        content: 'a to-do-list made with vue2 and vuex, the name already says what this projects do',
        image: '',
        skills: ''
    },
    {
        title: 'Pokedex', content: 'a totally useless project made for practicing',
        image: '',
        skills: ''
    },
    {
        title: 'Python', content: 'a fast project made with python',
        image: '',
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
    <div class="slider">
        <div v-for="(item, index) in items" :key="index" class="item" :style="getItemStyle(index)">
            <h1 class="font-black">{{ item.title }}</h1>
            <p class="font-black">{{ item.content }}</p>
        </div>
        <button id="next" @click="nextSlide">> </button>
        <button id="prev" @click="prevSlide">< </button>
    </div>
</template>

<style scoped>
.slider {
    position: relative;
    margin-top: 100px;
    width: 100%;
    height: 370px;
    overflow: hidden;
}

.item {
    position: absolute;
    width: 200px;
    height: 320px;
    text-align: justify;
    background-color: #fff;
    border-radius: 10px;
    padding: 20px;
    transition: 0.5s;
    left: calc(50% - 110px);
    top: 0;
}

#next {
    position: absolute;
    right: 50px;
    top: 40%;
}

#prev {
    position: absolute;
    left: 50px;
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