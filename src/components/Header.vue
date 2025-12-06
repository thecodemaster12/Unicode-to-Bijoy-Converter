<script setup>
import DarkModeToggle from './DarkModeToggle.vue';

</script>

<template>
    <section class="shadow dark:bg-gray-900 dark-transition dark:border-b dark:border-white">
        <div class="container mx-auto px-6 flex justify-between items-center py-3 md:py-6">
            <h2 class="text-2xl font-bold text-black dark:text-white">UniJoy</h2>
            <DarkModeToggle />
        </div>
    </section>
</template>

<style scoped>
</style>