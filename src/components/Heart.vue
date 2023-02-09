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
        <div class="flex justify-evenly">
            <div class="text-xl whitespace-pre-wrap" :class="[yesCount > 0 ? 'text-red-400' : 'text-red-700']">{{ response }}</div>
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