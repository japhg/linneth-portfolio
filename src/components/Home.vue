<script setup lang="ts">
import { computed, onBeforeUnmount, onMounted, ref } from 'vue'
import PrimaryButton from './PrimaryButton.vue'

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
    <div class="w-full">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 lg:gap-24 items-center">
            <!-- Content -->
            <div class="flex flex-col space-y-8 text-center lg:text-left">
                <div class="space-y-6">
                    <h1
                        class="text-4xl lg:text-6xl xl:text-7xl font-light leading-tight text-gray-900"
                        data-aos="fade-up"
                        data-aos-delay="0"
                        data-aos-duration="800"
                    >
                        <span class="block">Linneth Amante</span>
                        <span class="block font-medium">Gomera</span>
                    </h1>
                    
                    <div class="w-24 h-px bg-gray-300 mx-auto lg:mx-0"></div>
                    
                    <p
                        class="text-lg lg:text-xl text-gray-600 leading-relaxed max-w-lg"
                        data-aos="fade-up"
                        data-aos-delay="200"
                        data-aos-duration="800"
                    >
                        Tourism Graduate & Aspiring Model
                    </p>
                </div>

                <p
                    class="text-base lg:text-lg text-gray-500 leading-relaxed max-w-lg"
                    data-aos="fade-up"
                    data-aos-delay="400"
                    data-aos-duration="800"
                >
                    Discover the journey of a passionate individual bridging the worlds of travel, culture, and fashion. 
                    Explore creativity, professionalism, and unique perspectives.
                </p>

                <div
                    class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start"
                    data-aos="fade-up"
                    data-aos-delay="600"
                    data-aos-duration="800"
                >
                    <PrimaryButton
                        href="#my-journey"
                        class="bg-gray-900 hover:bg-gray-800 text-white px-8 py-4 text-sm font-medium uppercase tracking-wide transition-all duration-200"
                    >
                        Explore Journey
                    </PrimaryButton>
                    
                    <PrimaryButton
                        href="#portfolio"
                        class="border border-gray-300 hover:border-gray-400 text-gray-700 hover:text-gray-900 px-8 py-4 text-sm font-medium uppercase tracking-wide transition-all duration-200"
                    >
                        View Portfolio
                    </PrimaryButton>
                </div>
            </div>

            <!-- Image -->
            <div 
                class="relative"
                :data-aos="isDesktop ? 'fade-left' : 'fade-up'"
                data-aos-delay="200"
                data-aos-duration="800"
            >
                <div class="relative overflow-hidden rounded-lg shadow-2xl">
                    <img
                        src="/images/1.png"
                        alt="Linneth Gomera"
                        class="w-full h-auto object-cover transform hover:scale-105 transition-transform duration-700"
                    />
                    <div class="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent"></div>
                </div>
                
                <!-- Decorative elements -->
                <div class="absolute -top-4 -right-4 w-24 h-24 bg-gray-100 rounded-full opacity-50"></div>
                <div class="absolute -bottom-4 -left-4 w-16 h-16 bg-gray-200 rounded-full opacity-30"></div>
            </div>
        </div>
    </div>
</template>
