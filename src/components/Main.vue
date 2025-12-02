<!-- <template>
  <div class="converter-container">
    <h2>Bangla Unicode-Bijoy Converter</h2>
    <div class="text-areas">
      <div class="textarea-group">
        <label for="bijoyText">Bijoy Text</label>
        <textarea id="bijoyText" v-model="bijoyText" @input="bijoyToUnicode" placeholder="Type Bijoy text here..."></textarea>
      </div>
      <div class="textarea-group">
        <label for="unicodeText">Unicode Text</label>
        <textarea id="unicodeText" v-model="unicodeText" @input="unicodeToBijoy" placeholder="Type Unicode text here..."></textarea>
      </div>
    </div>
    <div class="buttons">
      <button @click="handleClear">Clear All</button>
    </div>
  </div>
</template> -->

<template>
    <section class="dark:bg-gray-900 dark-transition">
        <div class="container mx-auto px-6 h-full flex flex-col gap-6 justify-center items-center">
            <div class="">
                <!-- <Greetings :msg="message" /> -->
                 <p class="text-black dark:text-white">Uni: {{ unicodeText }}</p>
                 <p class="text-black dark:text-white">Bjo: {{ bijoyText }}</p>
            </div>

            <div class="w-full flex flex-col gap-4">
              <div class="relative">
                <textarea id="unicodeText" 
                class="w-full p-4 text-lg border rounded text-black dark:bg-gray-800 dark:text-white dark-transition" 
                rows="8" 
                v-model="unicodeText" 
                placeholder="Type Unicode text here...">
              </textarea>
              <!-- @input="unicodeToBijoy"  -->
                <PhClipboardText 
                @click="copyUni" 
                class="absolute top-1 right-1 cursor-pointer"
                :class="{ 'text-indigo-500': copied }"
                :size="26" />
              </div>

                <button @click="unicodeToBijoy">Uni to Bijoy</button>
                <button @click="bijoyToUnicode">Bijoy to Uni</button>
                
                <div class="relative">
                  <textarea id="bijoyText" 
                  class="w-full p-4 text-xl border rounded text-black dark:bg-gray-800 dark:text-white dark-transition font-smj" 
                  rows="8" 
                  v-model="bijoyText" 
                  placeholder="weRq †U·U..."></textarea>
                  <!-- @input="bijoyToUnicode"  -->

                  <PhClipboardText 
                  @click="copyBijoy" 
                  class="absolute top-1 right-1 cursor-pointer"
                  :class="{ 'text-indigo-500': copied }"
                  :size="26" />
                </div>
              </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue';
import { ConvertToUnicode, ConvertToASCII } from '../md';
import { PhClipboardText } from '@phosphor-icons/vue';

const bijoyText = ref('');
const unicodeText = ref('');
const copied = ref(false);

const bijoyToUnicode = () => {
  unicodeText.value = ConvertToUnicode(bijoyText.value);
};

const unicodeToBijoy = () => {
  bijoyText.value = ConvertToASCII(unicodeText.value);
};

const handleClear = () => {
  bijoyText.value = '';
  unicodeText.value = '';
};

const copyUni = () => {
  navigator.clipboard.writeText(unicodeText.value);
  copied.value = true;
  setTimeout(() => {
    copied.value = false;
  }, 1000);
}

const copyBijoy = () => {
  navigator.clipboard.writeText(bijoyText.value);
  copied.value = true;
  setTimeout(() => {
    copied.value = false;
  }, 1000);
}
</script>