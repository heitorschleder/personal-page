<script setup lang="ts">
import {
    Carousel,
    CarouselContent,
    CarouselItem,
} from '@/components/ui/carousel'
import cert1Image from '@/assets/images/certificado-1.png'
import cert2Image from '@/assets/images/certificado-2.png'
import cert3Image from '@/assets/images/certificado-3.png'
import Autoplay from 'embla-carousel-autoplay'
import { ref } from 'vue'

const degrees = [{
    id: 1,
    photo: cert1Image
},
{
    id: 2,
    photo: cert2Image
},
{
    id: 3,
    photo: cert3Image
}]

const showModal = ref(false)
const selectedPhoto = ref("")

const openModal = (photo: string) => {
    selectedPhoto.value = photo
    showModal.value = true
}

const closeModal = () => {
    showModal.value = false
    selectedPhoto.value = ""
}
</script>

<template>
    <section class="mt-14 mb-14 carousel-component flex flex-col align-middle items-center">
        <Carousel orientation="vertical" class="overflow-auto" :plugins="[Autoplay({
            delay: 2000,
        })]">
            <CarouselContent class="h-[300px]">
                <CarouselItem class="basis-1/3" v-for="certfies in degrees" :key="certfies.id">
                    <button @click="openModal(certfies.photo)">
                        <div class="h-72 w-72 sm:w-96">
                            <img :src="certfies.photo" alt="certified">
                        </div>
                    </button>
                </CarouselItem>
            </CarouselContent>
        </Carousel>
        <div v-if="showModal" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50">
            <div class="bg-white p-4 rounded">
                <button @click="closeModal" class="absolute top-2 right-2"><i class="text-5xl ti ti-xbox-x"></i></button>
                <img :src="selectedPhoto" alt="certified" class="max-w-full max-h-[80vh]">
            </div>
        </div>
    </section>
</template>