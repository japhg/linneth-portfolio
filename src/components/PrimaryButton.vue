<script setup lang="ts">
const props = defineProps<{
    type?: string
    href?: string
}>()
</script>
<template>
    <a v-if="props.href" :href="props.href" class="bg-primary px-8 py-3 text-white text-base">
        <slot />
    </a>
    <button v-else :type="props.type" class="bg-primary px-8 py-3 text-white text-base">
        <slot />
    </button>
</template>
