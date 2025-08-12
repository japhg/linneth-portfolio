<script setup lang="ts">
import { computed, onBeforeUnmount, onMounted, ref } from 'vue'

const screenWidth = ref(window.innerWidth)

const updateScreenWidth = () => {
    screenWidth.value = window.innerWidth
}

onMounted(() => {
    window.addEventListener('resize', updateScreenWidth)
})

onBeforeUnmount(() => {
    window.removeEventListener('resize', updateScreenWidth)
})

const isDesktop = computed(() => screenWidth.value >= 1024)
</script>
<template>
    <div class="w-full py-20 container mx-auto px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-5 md:gap-16 items-center">
            <div data-aos="fade-right" data-aos-delay="400" data-aos-duration="600">
                <h2 class="text-subHeading">
                    Discover the Journey of Linneth Gomera: Tourism Graduate and Aspiring Model
                </h2>
            </div>
            <div
                :data-aos="isDesktop ? 'fade-left' : 'fade-up'"
                data-aos-delay="400"
                data-aos-duration="600"
            >
                <p class="text-content text-justify font-normal leading-8">
                    Linneth Gomera graduated with a Bachelor's degree in Tourism, where she
                    developed a passion for travel and culture. Her journey into modeling began as a
                    creative outlet, allowing her to express her unique style and personality. With
                    a blend of education and artistry, Linneth is poised to make her mark in both
                    industries.
                </p>
            </div>
        </div>
    </div>
</template>
