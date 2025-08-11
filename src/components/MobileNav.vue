<script setup lang="ts">
import { ref } from 'vue'
import links from '@/data/links.json'
import CloseMenuIcon from './icons/CloseMenuIcon.vue'

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
        <div v-if="show" class="fixed inset-0 z-50 bg-black/50" @click.self="closeMenu">
            <Transition name="slide">
                <div
                    class="fixed inset-x-0 top-0 py-5 px-8 w-full border-primary border-b bg-white shadow-lg transform"
                >
                    <div class="flex justify-end p-3">
                        <button @click="closeMenu" class="p-2 text-gray-700">
                            <CloseMenuIcon />
                        </button>
                    </div>

                    <div class="text-gray-800 text-center flex flex-col gap-6">
                        <div v-for="link in links" :key="link.name">
                            <a
                                :href="link.url"
                                class="text-lg hover:text-primary transition-colors duration-200"
                                @click="closeMenu"
                            >
                                {{ link.name }}
                            </a>
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
    transition: transform 0.3s ease;
}

.slide-enter-from,
.slide-leave-to {
    transform: translateY(-100%);
}
</style>
