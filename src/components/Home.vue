<script setup lang="ts">
import PrimaryButton from './PrimaryButton.vue'
</script>

<template>
    <div class="w-full mt-10">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-14">
            <div class="flex flex-col gap-5">
                <h1
                    class="text-center md:text-start text-heading"
                >
                    Welcome to Linneth Gomera's Creative Portfolio
                </h1>

                <p class="text-content text-center md:text-start font-normal">
                    Explore the vibrant world of Linneth Gomera, a passionate Tourism Graduate and
                    aspiring Model. Discover her journey, creativity, and the projects that showcase
                    her unique talents.
                </p>

                <div class="flex justify-center md:justify-start">
                    <PrimaryButton
                        href="#my-journey"
                        class="bg-primary text-white py-2 md:py-4 px-4 md:px-6 text-content"
                    >
                        Explore
                    </PrimaryButton>
                </div>
            </div>
            <div class="w-full flex justify-center items-center">
                <img
                    src="/images/1.png"
                    alt=""
                    class="w-full md:w-4/5 h-auto object-cover rounded-lg"
                />
            </div>
        </div>
    </div>
</template>
