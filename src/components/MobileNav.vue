<script setup lang="ts">
import { ref } from 'vue'
import links from '@/data/links.json'
import CloseMenuIcon from './icons/CloseMenuIcon.vue'
import PrimaryButton from './PrimaryButton.vue'

defineProps<{
    show: boolean
}>()

const emit = defineEmits(['closeMenu'])
const closeMenu = () => {
    emit('closeMenu')
}
</script>

<template>
    <Transition name="fade">
        <div v-if="show" class="fixed inset-0 z-50 bg-black/60 backdrop-blur-sm" @click.self="closeMenu">
            <Transition name="slide">
                <div
                    class="fixed inset-x-0 top-0 py-6 px-6 w-full bg-white/95 backdrop-blur-md shadow-2xl border-b border-gray-100"
                >
                    <div class="flex justify-between items-center mb-8">
                        <h3 class="text-lg font-medium text-gray-900">Menu</h3>
                        <button 
                            @click="closeMenu" 
                            class="p-2 text-gray-600 hover:text-gray-900 hover:bg-gray-100 rounded-lg transition-all duration-200"
                        >
                            <CloseMenuIcon class="w-6 h-6" />
                        </button>
                    </div>

                    <div class="space-y-6">
                        <div v-for="link in links" :key="link.name" class="border-b border-gray-100 pb-4">
                            <a
                                :href="link.url"
                                class="text-lg font-medium text-gray-900 hover:text-gray-600 transition-colors duration-200 block"
                                @click="closeMenu"
                            >
                                {{ link.name }}
                            </a>
                        </div>
                        
                        <div class="pt-4">
                            <PrimaryButton
                                href="#contact"
                                class="bg-gray-900 hover:bg-gray-800 text-white px-6 py-3 text-sm font-medium uppercase tracking-wide transition-all duration-200 w-full"
                                @click="closeMenu"
                            >
                                Inquire
                            </PrimaryButton>
                        </div>
                    </div>
                </div>
            </Transition>
        </div>
    </Transition>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

.slide-enter-active,
.slide-leave-active {
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.slide-enter-from,
.slide-leave-to {
    transform: translateY(-100%);
    opacity: 0;
}
</style>
