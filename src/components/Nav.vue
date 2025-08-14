<script setup lang="ts">
import { RouterLink } from 'vue-router'
import links from '@/data/links.json'
import MobileNav from './MobileNav.vue'
import { ref } from 'vue'
import OpenMenuIcon from './icons/OpenMenuIcon.vue'
import CloseMenuIcon from './icons/CloseMenuIcon.vue'
import PrimaryButton from './PrimaryButton.vue'

const show = ref(false)

const closeMenu = () => {
    show.value = false
}
</script>

<template>
    <nav class="w-full">
        <div class="container mx-auto px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <!-- Logo -->
                <RouterLink to="/" class="flex items-center">
                    <img src="/images/linneth-logo.svg" alt="Linneth Logo" class="h-8 lg:h-10 w-auto" />
                </RouterLink>

                <!-- Mobile Menu Button -->
                <div class="flex md:hidden">
                    <button
                        type="button"
                        class="inline-flex items-center justify-center p-2 w-10 h-10 text-gray-600 hover:text-gray-900 hover:bg-gray-100 rounded-lg transition-all duration-200 focus:outline-none focus:ring-2 focus:ring-gray-200"
                        @click="show = !show"
                    >
                        <span class="sr-only">Open main menu</span>
                        <OpenMenuIcon v-if="!show" class="w-6 h-6" />
                        <CloseMenuIcon v-else class="w-6 h-6" />
                    </button>
                </div>

                <!-- Desktop Navigation -->
                <div class="hidden md:flex items-center space-x-8">
                    <div v-for="(link, key) in links" :key="key">
                        <a 
                            :href="link.url" 
                            class="text-gray-700 hover:text-gray-900 font-medium transition-colors duration-200 text-sm uppercase tracking-wide"
                        >
                            {{ link.name }}
                        </a>
                    </div>

                    <div class="ml-4">
                        <PrimaryButton
                            href="#contact"
                            class="bg-gray-900 hover:bg-gray-800 text-white px-6 py-3 text-sm font-medium uppercase tracking-wide transition-all duration-200"
                        >
                            Inquire
                        </PrimaryButton>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <MobileNav :show="show" @close-menu="closeMenu" />
</template>
