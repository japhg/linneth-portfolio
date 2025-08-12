<script setup lang="ts">
import EnvelopeIcon from './icons/EnvelopeIcon.vue';
import PrimaryButton from './PrimaryButton.vue'
</script>

<template>
    <div class="w-full py-20 container mx-auto px-8">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-5 md:gap-16 items-center">
            <div class="flex flex-col gap-4">
                <h2 class="text-subHeading">Let’s Create Together</h2>
                <p class="text-content font-normal leading-8 italic">
                    "Every journey starts somewhere. Let’s begin ours by creating beauty, capturing
                    moments, and telling stories together."
                </p>
            </div>

            <div class="flex flex-col gap-5 items-center justify-center">
                <PrimaryButton
                    href="mailto:linnethgomera05@gmail.com?subject=Inquire"
                    class="flex flex-wrap gap-2 justify-center items-center py-2 md:py-4 px-4 md:px-6 text-base md:text-lg"
                >
                    <EnvelopeIcon />
                    Send an inquiry!
                </PrimaryButton>
            </div>
        </div>
    </div>
</template>
