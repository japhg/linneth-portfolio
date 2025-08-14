<script setup lang="ts">
import trainings from '@/data/trainings.json'
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
                Professional Journey
            </h2>
            <div 
                class="w-24 h-px bg-gray-300 mx-auto mb-6"
                data-aos="fade-up"
                data-aos-delay="200"
                data-aos-duration="800"
            ></div>
            <p 
                class="text-lg text-gray-600 max-w-4xl mx-auto leading-relaxed"
                data-aos="fade-up"
                data-aos-delay="400"
                data-aos-duration="800"
            >
                Completed the Safety of Life at Sea (SOLAS) Training, an internationally recognized maritime certification focused on essential safety procedures, emergency preparedness, and crisis management to ensure the highest standards of passenger safety in maritime travel.
            </p>
        </div>

        <!-- Training Grid -->
        <div class="w-full max-w-7xl mx-auto">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div
                    v-for="(training, index) in trainings"
                    :key="index"
                    class="group"
                    data-aos="fade-up"
                    :data-aos-delay="200 * index"
                    data-aos-duration="800"
                >
                    <div class="relative overflow-hidden rounded-xl shadow-lg hover:shadow-2xl transition-all duration-500">
                        <div class="aspect-[4/5] bg-gray-200">
                            <img
                                :src="training.img"
                                :alt="training.title"
                                class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700"
                            />
                        </div>
                        <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
                    </div>

                    <div class="mt-6 text-center space-y-3">
                        <h3 class="text-xl font-medium text-gray-900 group-hover:text-gray-700 transition-colors">
                            {{ training.title }}
                        </h3>
                        <p class="text-gray-600 leading-relaxed">
                            {{ training.description }}
                        </p>
                    </div>
                </div>
            </div>
        </div>

        <!-- Additional Info -->
        <div class="mt-16 text-center">
            <div
                class="bg-gray-50 rounded-2xl p-8 lg:p-12 max-w-4xl mx-auto"
                data-aos="fade-up"
                data-aos-delay="800"
                data-aos-duration="800"
            >
                <h3 class="text-2xl font-medium text-gray-900 mb-4">
                    International Certification
                </h3>
                <p class="text-gray-600 leading-relaxed">
                    This comprehensive training demonstrates my commitment to safety, professionalism, and international standards. The SOLAS certification is recognized worldwide and showcases my dedication to maintaining the highest levels of safety and service excellence in any professional environment.
                </p>
            </div>
        </div>
    </div>
</template>
