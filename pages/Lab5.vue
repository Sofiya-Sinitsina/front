<template>
    <div class="flex flex-row max-sm:flex-col max-sm:flex-grow w-screen">
        <div class="min-w-[50%] flex flex-col justify-center gap-5 ml-10 max-sm:w-screen">
            <label><input class="mx-2" type="radio" value="choice" v-model="selectedvideo">How to choose the right strawberry seedlings</label>
            <label><input class="mx-2" type="radio" value="plant" v-model="selectedvideo">How to plant strawberries correctly</label>
            <label><input class="mx-2" type="radio" value="seeds" v-model="selectedvideo">How to grow high-yielding strawberries from seeds</label>
        </div>
        <div class="min-w-[50%] mt-11 max-sm:w-screen">
            <div v-if = "selectedvideo == 'choice'">
                <iframe width="600" height="340" frameborder="0" allowfullscreen
                src="https://www.youtube.com/embed/m0Eii--TrRI" class="max-sm:w-[90%]"></iframe>
            </div>
            <div v-if = "selectedvideo == 'plant'">
                <iframe width="600" height="340" frameborder="0" allowfullscreen
                src="https://www.youtube.com/embed/UesIehrAvrg" class="max-sm:w-[90%]"></iframe>
            </div>
            <div v-if = "selectedvideo == 'seeds'">
                <iframe width="600" height="340" frameborder="0" allowfullscreen
                src="https://www.youtube.com/embed/3pHS262Suss" class="max-sm:w-[90%]"></iframe>
            </div>
        </div>
    </div>

    <div class="flex flex-row mt-auto w-full mb-11 item-center justify-center gap-4 max-sm:flex-col max-sm:mt-11 max-sm:ml-11">
        <div>
            <h2>Imagine Dragons - Batle Cry</h2>
                <audio controls>
                <source src="/audio/idbc.mp3" type="audio/mpeg" />
                Ваш браузер не поддерживает тег аудио.
                </audio>
        </div>
        <div>
            <h2>Imagine Dragons - Digital</h2>
                <audio controls>
                <source src="/audio/idd.mp3" type="audio/mpeg" />
                Ваш браузер не поддерживает тег аудио.
                </audio>
        </div>
        <div>
            <h2>Imagine Dragons - Enemy (Feat. JID)</h2>
                <audio controls>
                <source src="/audio/ide.mp3" type="audio/mpeg" />
                Ваш браузер не поддерживает тег аудио.
                </audio>
        </div>
        </div>
</template>

<script setup lang = "ts">

const selectedvideo = ref<string>('')

</script>