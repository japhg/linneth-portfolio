<script setup lang="ts">
import About from '@/components/About.vue'
import Contact from '@/components/Contact.vue'
import ExploreMyJourney from '@/components/ExploreMyJourney.vue'
import Footer from '@/components/Footer.vue'
import Home from '@/components/Home.vue'
import Nav from '@/components/Nav.vue'
import PhotoShowcase from '@/components/PhotoShowcase.vue'

const year = new Date().getFullYear()
</script>

<template>
    <main class="w-full min-h-screen bg-white">
        <!-- Fixed Navigation -->
        <div
            class="fixed top-0 left-0 right-0 z-50 bg-white/95 backdrop-blur-md border-b border-gray-100"
        >
            <Nav />
        </div>

        <!-- Main Content -->
        <div class="pt-20">
            <!-- Hero Section -->
            <section
                class="relative min-h-screen flex items-center justify-center overflow-hidden"
                id="home"
            >
                <div class="absolute inset-0 bg-gradient-to-br from-gray-50 to-white"></div>
                <div class="relative container mx-auto px-6 lg:px-8">
                    <Home />
                </div>
            </section>

            <!-- About Section -->
            <section
                class="relative py-24 lg:py-32 bg-gradient-to-b from-white to-gray-50"
                id="about"
            >
                <div class="container mx-auto px-6 lg:px-8">
                    <About />
                </div>
            </section>

            <!-- Journey Section -->
            <section class="relative py-24 lg:py-32 bg-white" id="my-journey">
                <div class="container mx-auto px-6 lg:px-8">
                    <ExploreMyJourney />
                </div>
            </section>

            <!-- Portfolio Section -->
            <section
                class="relative py-24 lg:py-32 bg-gradient-to-b from-gray-50 to-white"
                id="portfolio"
            >
                <div class="container mx-auto px-6 lg:px-8">
                    <PhotoShowcase />
                </div>
            </section>

            <!-- Contact Section -->
            <section class="relative py-24 lg:py-32 bg-white" id="contact">
                <div class="container mx-auto px-6 lg:px-8">
                    <Contact />
                </div>
            </section>
        </div>
    </main>

    <!-- Footer -->
    <footer class="relative bg-white text-gray-900">
        <div class="container mx-auto px-6 lg:px-8 py-16">
            <Footer />
        </div>

        <div class="border-t border-gray-200">
            <div class="container mx-auto px-6 lg:px-8 py-8">
                <div class="flex flex-col md:flex-row justify-between items-center">
                    <span class="text-sm text-gray-600 font-light">
                        © {{ year }} Linneth Gomera. All rights reserved.
                    </span>
                    <div class="flex items-center space-x-6 mt-4 md:mt-0">
                        <span class="text-sm text-gray-600 font-light">Portfolio & Modeling</span>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>
