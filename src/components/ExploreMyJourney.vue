<script setup lang="ts">
import trainings from '@/data/trainings.json'
</script>
<template>
    <div class="w-full py-20">
        <div class="flex flex-col justify-start gap-5 text-center mb-20">
            <h2 class="text-subHeading">Explore My Journey: The SOLAS Training Experience</h2>

            <p class="text-base max-w-4xl mx-auto">
                Completed the Safety of Life at Sea (SOLAS) Training, an internationally recognized
                maritime certification focused on essential safety procedures, emergency
                preparedness, and crisis management to ensure the highest standards of passenger
                safety in maritime travel.
            </p>
        </div>

        <!-- Photo Grid -->
        <div class="w-full">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-7xl mx-auto">
                <div
                    v-for="(training, index) in trainings"
                    :key="index"
                    class="flex flex-col gap-4 items-center text-center group"
                    data-aos="fade-up"
                    :data-aos-delay="200 * index"
                    data-aos-duration="600"
                >
                    <div
                        class="rounded-xl overflow-hidden w-full aspect-[4/5] shadow-lg group-hover:shadow-xl transition-all duration-300 group-hover:scale-[1.02]"
                    >
                        <img
                            :src="training.img"
                            :alt="training.title"
                            class="w-full h-full object-cover"
                        />
                    </div>

                    <div class="space-y-2">
                        <h3
                            class="text-lg font-playfair font-semibold text-gray-800 group-hover:text-gray-900 transition-colors"
                        >
                            {{ training.title }}
                        </h3>

                        <p class="text-sm text-gray-600 leading-relaxed max-w-xs">
                            {{ training.description }}
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
