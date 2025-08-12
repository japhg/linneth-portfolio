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
    <div class="grid grid-cols-1 md:grid-cols-3 text-center md:text-start gap-5 py-16">
        <div class="col-span-1 flex justify-center md:justify-start">
            <RouterLink to="/">
                <img src="/images/linneth-logo.svg" alt="Linneth Logo" class="h-auto" />
            </RouterLink>
        </div>

        <div class="col-span-2 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5 lg:gap-0">
            <div class="flex flex-col gap-2 font-playfair">
                <h6 class="text-content font-medium">Explore</h6>

                <a
                    v-for="(explore, exploreIndex) in exploreLinks"
                    :key="exploreIndex"
                    :href="explore.url"
                    class="text-sm hover:underline hover:text-primary transition-all ease-in-out"
                >
                    {{ explore.title }}
                </a>
            </div>
            <div class="flex flex-col gap-2">
                <h6 class="text-content font-medium font-playfair">Get In Touch</h6>

                <a
                    href="mailto:linnethgomera05@gmail.com?subject=Inquire"
                    class="text-sm hover:underline hover:text-primary transition-all ease-in-out"
                >
                    linnethgomera05@gmail.com
                </a>
            </div>
            <div class="flex flex-col gap-2">
                <h6 class="text-content font-medium">Follow me:</h6>

                <div class="flex justify-center md:justify-start items-center gap-5">
                    <a href="https://www.facebook.com/linneth.gomera.5">
                        <FacebookIcon
                            class="w-8 h-8 hover:fill-primary transition-all ease-in-out"
                        />
                    </a>
                    <a href="https://www.instagram.com/Linneth%20gomera">
                        <InstagramIcon
                            class="w-8 h-8 hover:fill-primary transition-all ease-in-out"
                        />
                    </a>
                    <a href="https://www.tiktok.com/@msluna555">
                        <TiktokIcon class="w-8 h-8 hover:fill-primary transition-all ease-in-out" />
                    </a>
                    <a href="https://www.linkedin.com/in/linneth-gomera-85731a372/">
                        <LinkedinIcon
                            class="w-8 h-8 hover:fill-primary transition-all ease-in-out"
                        />
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>
