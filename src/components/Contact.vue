<script setup lang="ts">
import { computed, onBeforeUnmount, onMounted, ref } from 'vue';
import EnvelopeIcon from './icons/EnvelopeIcon.vue';
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
        <!-- Header -->
        <div class="text-center mb-16">
            <h2 
                class="text-3xl lg:text-4xl xl:text-5xl font-light text-gray-900 mb-6"
                data-aos="fade-up"
                data-aos-delay="0"
                data-aos-duration="800"
            >
                Let's Create Together
            </h2>
            <div 
                class="w-24 h-px bg-gray-300 mx-auto mb-6"
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
                        Ready to Start Your Project?
                    </h3>
                    
                    <div class="w-16 h-px bg-gray-300"></div>
                </div>

                <div class="space-y-6 text-gray-600 leading-relaxed">
                    <p class="text-lg italic">
                        "Every journey starts somewhere. Let's begin ours by creating beauty, capturing moments, and telling stories together."
                    </p>
                    
                    <p class="text-lg">
                        Let's connect and explore how we can work together to create something extraordinary.
                    </p>
                </div>

                <!-- Contact Info -->
                <div class="space-y-4">
                    <div class="flex items-center space-x-4">
                        <div class="w-12 h-12 bg-gray-100 rounded-full flex items-center justify-center">
                            <EnvelopeIcon class="w-6 h-6 text-gray-600" />
                        </div>
                        <div>
                            <p class="text-sm font-medium text-gray-900">Email</p>
                            <p class="text-gray-600">linnethgomera05@gmail.com</p>
                        </div>
                    </div>
                    
                    <div class="flex items-center space-x-4">
                        <div class="w-12 h-12 bg-gray-100 rounded-full flex items-center justify-center">
                            <svg class="w-6 h-6 text-gray-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path>
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path>
                            </svg>
                        </div>
                        <div>
                            <p class="text-sm font-medium text-gray-900">Location</p>
                            <p class="text-gray-600">Available for travel worldwide</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Contact Form/Call to Action -->
            <div 
                class="relative"
                :data-aos="isDesktop ? 'fade-left' : 'fade-up'"
                data-aos-delay="600"
                data-aos-duration="800"
            >
                <div class="bg-gray-50 rounded-2xl p-8 lg:p-12 shadow-lg">
                    <div class="text-center space-y-6">
                        <div class="w-16 h-16 bg-gray-100 rounded-full flex items-center justify-center mx-auto">
                            <EnvelopeIcon class="w-8 h-8 text-gray-600" />
                        </div>
                        
                        <div class="space-y-4">
                            <h3 class="text-2xl font-medium text-gray-900">
                                Get in Touch
                            </h3>
                            <p class="text-gray-600">
                                Ready to discuss your project? Send me a message and let's start creating something amazing together.
                            </p>
                        </div>

                        <div class="pt-4">
                            <PrimaryButton
                                href="mailto:linnethgomera05@gmail.com?subject=Inquiry - Portfolio"
                                class="bg-gray-900 hover:bg-gray-800 text-white px-8 py-4 text-sm font-medium uppercase tracking-wide transition-all duration-200 w-full lg:w-auto"
                            >
                                Send Inquiry
                            </PrimaryButton>
                        </div>
                    </div>
                </div>
                
                <!-- Decorative elements -->
                <div class="absolute -top-4 -right-4 w-24 h-24 bg-gray-100 rounded-full opacity-50"></div>
                <div class="absolute -bottom-4 -left-4 w-16 h-16 bg-gray-200 rounded-full opacity-30"></div>
            </div>
        </div>
    </div>
</template>
