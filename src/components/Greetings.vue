<script setup>
const props = defineProps(
    {
        msg: Object
    }
)
</script>

<template>
    <h1 class="text-2xl md:text-4xl text-center text-black dark:text-white mb-2">{{ msg.title }}</h1>
    <p class="text-sm md:text-xl text-center text-gray-500 dark:text-gray-400">{{ msg.description }}</p>
</template>