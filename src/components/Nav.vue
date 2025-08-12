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
    <nav class="w-full mx-auto">
        <div class="flex justify-between items-center px-5 md:px-28 gap-2 h-20 mx-auto">
            <!-- Logo -->
            <RouterLink to="/">
                <img src="/images/linneth-logo.svg" alt="Linneth Logo" class="h-auto" />
            </RouterLink>

            <div class="flex flex-end justify-end md:hidden px-2 w-full">
                <button
                    data-collapse-toggle="navbar-sticky"
                    type="button"
                    class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden focus:outline-none focus:ring-2"
                    aria-controls="navbar-sticky"
                    aria-expanded="false"
                    @click="show = !show"
                >
                    <span class="sr-only">Open main menu</span>
                    <OpenMenuIcon v-if="!show" />

                    <CloseMenuIcon v-else="show" />
                </button>
            </div>

            <!-- Nav Links -->
            <div class="gap-6 hidden md:flex">
                <div v-for="(link, key) in links" :key="key">
                    <a :href="link.url" class="font-hover:text-accent hover:text-primary transition-colors ease-in-out text-lg">
                        {{ link.name }}
                    </a>
                </div>

                <div>
                    <PrimaryButton
                        href="#contact"
                        class="py-4 px-6 text-lg"
                    >
                        Inquire
                    </PrimaryButton>
                </div>
            </div>
        </div>
    </nav>

    <MobileNav :show="show" @close-menu="closeMenu" />
</template>
