<template>
    <header class="flex flex-row w-full shadow-md max-sm:justify-between relative">
        <div class="basis-1/4 items-center justify-start px-4 min-w-40 max-sm:basis-auto">
            <img src="assets/img/logo.png" class="w-16 h-16">
        </div>
        <div class="basis-1/4 max-sm:basis-auto">

        </div>
        <nav :class="{'basis-1/2 flex flex-row items-center justify-end px-4 gap-4' : !burger || burger, 
        'max-sm:basis-auto max-sm:absolute max-sm:top-full max-sm:w-full max-sm:justify-center max-sm:flex-col max-sm:gap-0 max-sm:px-0' : burger,
        'max-sm:hidden' : !burger}">
            <NuxtLink to="/" class="my-auto p-2 bg-gradient-to-t from-[#C822FF] to-[#1A6DFF] inline-block text-transparent bg-clip-text hover:text-xl max-sm:w-full max-sm:text-center">Home</NuxtLink>
            <div class="my-auto p-2 bg-gradient-to-t from-[#C822FF] to-[#1A6DFF] inline-block text-transparent bg-clip-text hover:text-xl max-sm:w-full max-sm:text-center max-sm:px-0 max-sm:pb-0" @click="switch_submenu">Labs
                <div class="flex flex-col absolute top-full w-56 text-center max-sm:relative max-sm:w-full bg-white" v-show="submenu">
                    <NuxtLink to="/Lab3" class="my-auto p-2 border-b-2 border-t-2 border-[#390c47] bg-gradient-to-t from-[#4817588c] to-[#02215781] inline-block text-transparent bg-clip-text hover:text-xl max-sm:w-full max-sm:text-center hover:bg-[#b3b3b3] ">Lab3</NuxtLink>
                    <NuxtLink to="/Lab4" class="my-auto p-2 border-b-2 border-[#390c47] bg-gradient-to-t from-[#4817588c] to-[#02215781] inline-block text-transparent bg-clip-text hover:text-xl max-sm:w-full max-sm:text-center hover:bg-[#b3b3b3]">Lab4</NuxtLink>
                    <NuxtLink to="/Lab5" class="my-auto p-2 border-b-2 border-[#390c47] bg-gradient-to-t from-[#4817588c] to-[#02215781] inline-block text-transparent bg-clip-text hover:text-xl max-sm:w-full max-sm:text-center hover:bg-[#b3b3b3]">Lab5</NuxtLink>
                    <NuxtLink to="/Lab6" class="my-auto p-2 border-b-2 border-[#390c47] bg-gradient-to-t from-[#4817588c] to-[#02215781] inline-block text-transparent bg-clip-text hover:text-xl max-sm:w-full max-sm:text-center hover:bg-[#b3b3b3]">Lab6</NuxtLink>
                </div>
            </div>
            <NuxtLink to="/login" class="my-auto p-2 bg-gradient-to-t from-[#C822FF] to-[#1A6DFF] inline-block text-transparent bg-clip-text hover:text-xl max-sm:w-full max-sm:text-center">LogIn</NuxtLink>
            <NuxtLink to="/logout" class="my-auto p-2 bg-gradient-to-t from-[#C822FF] to-[#1A6DFF] inline-block text-transparent bg-clip-text hover:text-xl max-sm:w-full max-sm:text-center">LogOut</NuxtLink>
        </nav>
        <div v-if = "!burger" @click = "switch_burger" class="max-sm:flex max-sm:flex-col max-sm:mr-8 max-sm:mt-4 max-sm:justify-between max-sm:items-center max-sm:w-8 max-sm:h-6">
            <span class="h-[3px] w-full bg-[#390c47]"></span>
            <span class="h-[3px] w-full bg-[#390c47]"></span>
            <span class="h-[3px] w-full bg-[#390c47]"></span>
        </div>
        <div v-else class="max-sm:flex max-sm:flex-col max-sm:mr-8 max-sm:mt-4 max-sm:justify-between max-sm:items-center max-sm:w-8 max-sm:h-6" @click = "switch_burger">
            <span class="h-[3px] w-full bg-[#390c47] rotate-45 relative top-[9px]"></span>
            <span class="h-[3px] w-full bg-[#390c47] opacity-0"></span>
            <span class="h-[3px] w-full bg-[#390c47] rotate-[-45deg] relative bottom-3"></span>
        </div>
    </header>

    <main class="p-5 flex min-h-screen flex-wrap">
        <slot />
    </main>

    <footer class="flex flex-row mt-auto w-full bg-gradient-to-t from-[#C822FF] to-[#1A6DFF] items-center justify-center px-4 py-2 gap-4">
        <a href="https://github.com/"><img src="assets/img/git.png" class="w-16 h-16"></a>
    </footer>
</template>

<script setup lang="ts">
import { useHead } from '#app';
import {ref} from 'vue';

useHead({
    script: [
        {
            async: true,
            src: 'https://www.googletagmanager.com/gtag/js?id=G-5W0TCGQL0C'
        },
        {
            innerHTML: `
            window.dataLayer = window.dataLayer || [];
            function gtag(){dataLayer.push(arguments);}
            gtag('js', new Date());
            gtag('config', 'G-5W0TCGQL0C');
            `,
            type: 'text/javascript',
        },
    ],
    __dangerouslyDisableSanitizersByTagID: {
        gtag: ['innerHTML'],
    },
});

const burger = ref<boolean>(false)
const submenu = ref<boolean>(false)

const switch_burger = () => {burger.value = !burger.value}
const switch_submenu = () => {submenu.value = !submenu.value}

</script>