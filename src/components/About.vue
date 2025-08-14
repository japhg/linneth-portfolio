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
    <div class="w-full">
        <div class="text-center mb-16">
            <h2 
                class="text-3xl lg:text-4xl xl:text-5xl font-light text-gray-900 mb-6"
                data-aos="fade-up"
                data-aos-delay="0"
                data-aos-duration="800"
            >
                About Linneth
            </h2>
            <div 
                class="w-24 h-px bg-gray-300 mx-auto"
                data-aos="fade-up"
                data-aos-delay="200"
                data-aos-duration="800"
            ></div>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 lg:gap-24 items-center">
            <!-- Content -->
            <div 
                class="space-y-8"
                data-aos="fade-right"
                data-aos-delay="400"
                data-aos-duration="800"
            >
                <div class="space-y-6">
                    <h3 class="text-2xl lg:text-3xl font-medium text-gray-900">
                        Tourism Graduate | Aspiring Flight Attendant & Model
                    </h3>
                    
                    <div class="w-16 h-px bg-gray-300"></div>
                </div>

                <div class="space-y-6 text-gray-600 leading-relaxed">
                    <p class="text-lg">
                        Linneth Gomera graduated with a Bachelor's degree in Tourism, where she developed a deep passion for travel, culture, and human connection. Her academic journey provided her with a unique perspective on global diversity and cultural appreciation.
                    </p>
                    
                    <p class="text-lg">
                        Her transition into modeling began as a creative outlet, allowing her to express her unique style and personality while bridging her understanding of different cultures and aesthetics. With a blend of education and artistry, Linneth is poised to make her mark in both industries.
                    </p>
                    
                    <p class="text-lg">
                        Her approach combines professionalism with authenticity, bringing a fresh perspective to the modeling industry through her background in tourism and cultural studies.
                    </p>
                </div>

                <div class="flex flex-wrap gap-4">
                    <div class="bg-gray-100 px-4 py-2 rounded-full">
                        <span class="text-sm font-medium text-gray-700">Tourism Graduate</span>
                    </div>
                    <div class="bg-gray-100 px-4 py-2 rounded-full">
                        <span class="text-sm font-medium text-gray-700">Cultural Enthusiast</span>
                    </div>
                    <div class="bg-gray-100 px-4 py-2 rounded-full">
                        <span class="text-sm font-medium text-gray-700">Aspiring Model</span>
                    </div>
                    <div class="bg-gray-100 px-4 py-2 rounded-full">
                        <span class="text-sm font-medium text-gray-700">Future Flight Attendant</span>
                    </div>
                </div>
            </div>

            <!-- Image -->
            <div 
                class="relative"
                :data-aos="isDesktop ? 'fade-left' : 'fade-up'"
                data-aos-delay="600"
                data-aos-duration="800"
            >
                <div class="relative overflow-hidden rounded-lg shadow-2xl">
                    <img
                        src="/images/2.jpg"
                        alt="Linneth Gomera - About"
                        class="w-full h-auto object-cover"
                    />
                    <div class="absolute inset-0 bg-gradient-to-t from-black/30 to-transparent"></div>
                </div>
                
                <!-- Decorative elements -->
                <div class="absolute -top-6 -right-6 w-32 h-32 bg-gray-100 rounded-full opacity-40"></div>
                <div class="absolute -bottom-6 -left-6 w-20 h-20 bg-gray-200 rounded-full opacity-30"></div>
            </div>
        </div>
    </div>
</template>
