<template>
    <main class="flex-col flex-grow">
        <div class="flex w-screen h-16 justify-center items-center gap-4">
            <label><input class="mx-2" type="radio" value="all" v-model="selectedcategory">All</label>
            <label class="text-purple-500"><input class="mx-2" type="radio" value="ever" v-model="selectedcategory">Everbearing strawberries</label>
            <label class="text-purple-900"><input class="mx-2" type="radio" value="june" v-model="selectedcategory">June-bearing strawberries</label>
        </div>
        <div class="flex gap-4 justify-center items-center flex-wrap">
            <div class="ever" v-if = "selectedcategory == 'all' || selectedcategory == 'ever'">
                <img :src="albion_r.image" class="w-60 pt-2">
                <p class="text-purple-500 text-xl">Albion</p>
            </div>

            <div class="june" v-if = "selectedcategory == 'all' || selectedcategory == 'june'">
                <img :src="ami.image" class="w-60 pt-2">
                <p class="text-purple-900 text-xl">Ami</p>
            </div>

            <div class="june" v-if = "selectedcategory == 'all' || selectedcategory == 'june'">
                <img :src="aziya.image" class="w-60 pt-2">
                <p class="text-purple-900 text-xl">Aziya</p>
            </div>

            <div class="june" v-if = "selectedcategory == 'all' || selectedcategory == 'june'">
                <img :src="brilla.image" class="w-60 pt-2">
                <p class="text-purple-900 text-xl">Brilla</p>
            </div>

            <div class="june" v-if = "selectedcategory == 'all' || selectedcategory == 'june'">
                <img :src="kimberli.image" class="w-60 pt-2">
                <p class="text-purple-900 text-xl">Kimberli</p>
            </div>

            <div class="june" v-if = "selectedcategory == 'all' || selectedcategory == 'june'">
                <img :src="kupchikha.image" class="w-60 pt-2">
                <p class="text-purple-900 text-xl">Kupchikha</p>
            </div>

            <div class="june" v-if = "selectedcategory == 'all' || selectedcategory == 'june'">
                <img :src="magnus.image" class="w-60 pt-2">
                <p class="text-purple-900 text-xl">Magnus</p>
            </div>

            <div class="ever" v-if = "selectedcategory == 'all' || selectedcategory == 'ever'">
                <img :src="san_andreas_r.image" class="w-60 pt-2">
                <p class="text-purple-500 text-xl">San-andreas</p>
            </div>

            <div class="june" v-if = "selectedcategory == 'all' || selectedcategory == 'june'">
                <img :src="sibilla.image" class="w-60 pt-2">
                <p class="text-purple-900 text-xl">Sibilla</p>
            </div>

            <div class="ever" v-if = "selectedcategory == 'all' || selectedcategory == 'ever'">
                <img :src="silva_r.image" class="w-60 pt-2">
                <p class="text-purple-500 text-xl">Silva</p>
            </div>
        </div>
    </main>
</template>

<script setup lang = "ts">

import { reactive } from 'vue'

interface berries {
    name: string,
    image: string
}

const albion_r = reactive<berries>({
    name: 'albion',
    image: '/img/sb/albion_r.jpg'
})

const ami = reactive<berries>({
    name: 'ami',
    image: '/img/sb/ami.jpg'
})

const aziya = reactive<berries>({
    name: 'aziya',
    image:'/img/sb/aziya.jpg'
})

const brilla = reactive<berries>({
    name: 'brilla',
    image: '/img/sb/brilla.jpg'
})

const kimberli = reactive<berries>({
    name: 'kimberli',
    image: '/img/sb/kimberli.jpg'
})

const kupchikha = reactive<berries>({
    name: 'kupchikha',
    image: '/img/sb/kupchikha.jpg'
})

const magnus = reactive<berries>({
    name: 'magnus',
    image: '/img/sb/magnus.jpg'
})

const san_andreas_r = reactive<berries>({
    name: 'san-andreas',
    image: '/img/sb/san-andreas_r.jpg'
})

const sibilla = reactive<berries>({
    name: 'sibilla',
    image: '/img/sb/sibilla.jpg'
})

const silva_r = reactive<berries>({
    name: 'silva',
    image: '/img/sb/silva_r.jpg'
})

const genever = reactive<berries[]>([
    {name: 'albion', image: '/img/sb/albion_r.jpg'},
    {name: 'san-andreas_r', image: '/img/sb/san-andreas_r.jpg'},
    {name: 'silva', image: '/img/sb/silva_r.jpg'}
])

const genjune = reactive<berries[]>([
    {name: 'ami', image: '/img/sb/ami.jpg'},
    {name: 'aziya', image:'/img/sb/aziya.jpg'},
    {name: 'brilla', image: '/img/sb/brilla.jpg'},
    {name: 'kupchikha', image: '/img/sb/kupchikha.jpg'},
    {name: 'kimberli', image: '/img/sb/kimberli.jpg'},
    {name: 'magnus', image: '/img/sb/magnus.jpg'},
    {name: 'sibilla', image: '/img/sb/sibilla.jpg'}
])

const selectedcategory = ref<string>('')

</script>

<style scoped>

.ever {
    @apply flex flex-col gap-2 border-purple-500 border-4 w-72 h-auto items-center rounded-xl
}

.june {
    @apply flex flex-col gap-2 border-purple-900 border-4 w-72 h-auto items-center rounded-xl
}

</style>