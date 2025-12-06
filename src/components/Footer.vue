<script setup>
import { PhGithubLogo, PhUser } from '@phosphor-icons/vue';

</script>

<template>
    <footer>
        <div class="bg-black text-white py-4 md:py-6">
            <ul class="flex text-2xl justify-center items-center gap-2">
                <li><a class="hover:text-gray-400" href="https://github.com/thecodemaster12" target="_blank"> <PhGithubLogo class="text-2xl md:text-3xl hover:scale-105" /> </a></li>
                <li><a class="hover:text-gray-400" href="https://sr-shihab.netlify.app/" target="_blank"> <PhUser class="text-2xl md:text-3xl hover:scale-105" /> </a></li>
            </ul>
        </div>
    </footer>
</template>

<style scoped>
</style>