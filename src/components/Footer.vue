<script setup lang="ts">
import { RouterLink } from 'vue-router'
import FacebookIcon from './icons/FacebookIcon.vue'
import InstagramIcon from './icons/InstagramIcon.vue'
import TiktokIcon from './icons/TiktokIcon.vue'
import LinkedinIcon from './icons/LinkedinIcon.vue'

const exploreLinks = [
    { title: 'Home', url: '#home' },
    { title: 'About', url: '#about' },
    { title: 'Portfolio', url: '#portfolio' },
    { title: 'Explore My Journey', url: '#my-journey' },
]
</script>

<template>
    <div class="grid grid-cols-1 lg:grid-cols-4 gap-12">
        <!-- Brand -->
        <div class="lg:col-span-1">
            <RouterLink to="/" class="inline-block">
                <img src="/images/linneth-logo.svg" alt="Linneth Logo" class="h-10 w-auto mb-6" />
            </RouterLink>
            <p class="text-gray-600 text-sm leading-relaxed">
                Tourism Graduate & Aspiring Model. Creating beauty, capturing moments, and telling
                stories through professional modeling and creative collaboration.
            </p>
        </div>

        <!-- Navigation -->
        <div class="lg:col-span-1">
            <h6 class="text-gray-900 font-medium text-sm uppercase tracking-wide mb-6">
                Navigation
            </h6>
            <div class="space-y-3">
                <a
                    v-for="(explore, exploreIndex) in exploreLinks"
                    :key="exploreIndex"
                    :href="explore.url"
                    class="block text-gray-600 hover:text-gray-900 transition-colors duration-200 text-sm"
                >
                    {{ explore.title }}
                </a>
            </div>
        </div>

        <!-- Contact -->
        <div class="lg:col-span-1">
            <h6 class="text-gray-900 font-medium text-sm uppercase tracking-wide mb-6">Contact</h6>
            <div class="space-y-3">
                <a
                    href="mailto:linnethgomera05@gmail.com?subject=Inquiry - Portfolio"
                    class="block text-gray-600 hover:text-gray-900 transition-colors duration-200 text-sm"
                >
                    linnethgomera05@gmail.com
                </a>
                <p class="text-gray-600 text-sm">Available for travel worldwide</p>
            </div>
        </div>

        <!-- Social -->
        <div class="lg:col-span-1">
            <h6 class="text-gray-900 font-medium text-sm uppercase tracking-wide mb-6">Follow</h6>
            <div class="flex space-x-4">
                <a
                    href="https://www.facebook.com/linneth.gomera.5"
                    class="w-10 h-10 bg-gray-100 hover:bg-gray-200 rounded-full flex items-center justify-center transition-colors duration-200"
                >
                    <FacebookIcon class="w-5 h-5 text-gray-600" />
                </a>
                <a
                    href="https://www.instagram.com/raya_urassaya"
                    class="w-10 h-10 bg-gray-100 hover:bg-gray-200 rounded-full flex items-center justify-center transition-colors duration-200"
                >
                    <InstagramIcon class="w-5 h-5 text-gray-600" />
                </a>
                <a
                    href="https://www.tiktok.com/@msluna555"
                    class="w-10 h-10 bg-gray-100 hover:bg-gray-200 rounded-full flex items-center justify-center transition-colors duration-200"
                >
                    <TiktokIcon class="w-5 h-5 text-gray-600" />
                </a>
                <a
                    href="https://www.linkedin.com/in/linneth-gomera-85731a372/"
                    class="w-10 h-10 bg-gray-100 hover:bg-gray-200 rounded-full flex items-center justify-center transition-colors duration-200"
                >
                    <LinkedinIcon class="w-5 h-5 text-gray-600" />
                </a>
            </div>
        </div>
    </div>
</template>
