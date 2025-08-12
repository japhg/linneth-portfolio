<script setup lang="ts">
import { RouterView } from 'vue-router'
import AOS from "aos";
import "aos/dist/aos.css";

AOS.init();
</script>

<template>
    <div class="font-lora">
        <RouterView />
    </div>
</template>
