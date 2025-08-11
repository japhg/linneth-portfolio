<script setup lang="ts">
import About from '@/components/About.vue'
import Contact from '@/components/Contact.vue'
import ExploreMyJourney from '@/components/ExploreMyJourney.vue'
import Footer from '@/components/Footer.vue'
import Home from '@/components/Home.vue'
import Nav from '@/components/Nav.vue'
import PhotoShowcase from '@/components/PhotoShowcase.vue'
import Section from '@/components/Section.vue'

const year = new Date().getFullYear()
</script>

<template>
    <main class="w-full min-h-screen flex flex-col">
        <Nav />

        <div class="flex-1 flex flex-col items-center">
            <div class="container mx-auto px-4" id="home">
                <Section class="h-fit lg:h-screen">
                    <Home />
                </Section>
            </div>

            <div class="w-full bg-primary-lighter" id="about">
                <Section>
                    <About />
                </Section>
            </div>

            <div class="container mx-auto px-4" id="my-journey">
                <Section class="">
                    <ExploreMyJourney />
                </Section>
            </div>

            <div class="w-full bg-primary-lighter py-20" id="portfolio">
                <div class="container mx-auto px-4">
                    <PhotoShowcase />
                </div>
            </div>

            <div class="w-full" id="contact">
                <Section>
                    <Contact />
                </Section>
            </div>
        </div>
    </main>

    <hr class="border border-primary-lighter mx-10" />

    <footer class="w-full">
        <div class="container mx-auto px-4">
            <Footer />
        </div>

        <hr class="border border-primary-lighter mx-10" />

        <div class="container mx-auto px-4 text-center">
            <span class="text-sm font-playfair">@ {{ year }} Linneth. All rights reserved.</span>
        </div>
    </footer>
</template>
