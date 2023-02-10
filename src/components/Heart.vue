<template>
    <div>
        <div class="flex justify-center align-center w-full h-60">
            <img src="../assets/heart.svg" class="" alt="heart" />
        </div>
        <div class="flex justify-center align-center pt-3">
            <p class="text-3xl pb-3 w-72">Amina, will you be my valentine?</p>
        </div>
        <div class="flex justify-evenly pb-3">
            <button type="button" v-if="yesCount === 0" @click="yesCount++">Yes</button>
            <button type="button" v-if="noCount === 0 && yesCount === 0" @click="noCount++">No</button>
        </div>
        <div class="flex justify-evenly flex-col" v-if="response.length > 0">
            <div class="text-xl whitespace-pre-wrap" :class="[yesCount > 0 ? 'text-red-400' : 'text-red-700']">
                {{ response }}
            </div>
            <div class="text-xl py-3">
                Scroll down 
            </div>
            <div class="flex items-center flex-col w-auto">
                <img class="object-cover rounded-lg shadow-lg lg:max-w-lg" src="../assets/1.jpg" alt="Love">
                <p class="py-3">Thank you</p>
                <img class="object-cover rounded-lg shadow-lg lg:max-w-lg" src="../assets/2.jpg" alt="Love">
                <p class="py-3">for being</p>
                <img class="object-cover rounded-lg shadow-lg lg:max-w-lg" src="../assets/3.jpg" alt="Love">
                <p class="py-3">with me</p>
                <img class="object-cover rounded-lg shadow-lg lg:max-w-lg" src="../assets/4.jpg" alt="Love">
                <p class="py-3">I want to be with you always</p>
                <img class="object-cover rounded-lg shadow-lg lg:max-w-lg" src="../assets/5.jpg" alt="Love">
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
    import { ref, watch } from 'vue'

    const yesCount = ref(0)
    const noCount = ref(0)
    let response = ''

    watch(noCount, (count) => {
        if (count > 0) {
            response = 'Wrong Answer'
        }
    })

    watch(yesCount, (count) => {
        if (count > 0) {
            response = 'I Love You 💖\n' +
            'Meeting you was the best thing that has ever happened to me'
        }
    })
</script>

<style scoped>

</style>